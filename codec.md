# DBUF Codec

DBUF is structured as a series of 32-bit blocks. The default encoding of a block contains packed variable length integers (hereafter "varints") representing symbols from the registry. Certain symbols can describe the encoding of later blocks, such as an (IEEE 754 binary64) occupying 2 blocks or a varint representing a number instead of a symbol. 32-bit alignment is maintained throughout a stream providing opportunities for low-level optimization.

## Packed varints

A 32-bit varint block is divided into 8 description bits (most significant bits) and 24 data bits (least significant bits). Each description bit corresponds to 3 data bits according to its relative position. Varints are formed by alternating sequences of description bits. For example, the description bits 11000111 means 3 varints of (6, 9, 9) bits, respectively. 

The last varint of a block may continue in the next varint block by beginning with a zero description bit. For example, description bits 01000011 in a block following the above example would mean the third varint is 12 bits instead of 9. Conversely, a description of 10110001 would not continue the last varint and begin with a separate 3 bit varint. This means that a parser must buffer a partial value for the last varint until it reads the next varint block.

While a single varint encoding can continue indefinitely by using a zero description bit, the maximum data value of a varint is 32 bits (unsigned). This is so decoding can be optimized with only 32-bit shift instructions. For example a 36-bit data value will have its 4 most significant bits discarded by the way shift instructions are commonly implemented. Values larger than 2^32-1 will use symbols to encode them into non-varint blocks. 

Blocks are in network byte order (big-endian), meaning the description bits are in the first byte. The individual varints are also big-endian. This format is also convenient on little-endian systems because it only requires a single swap at the 32-bit level; then, all other decoding steps are the same.

While using 25% of the bits as description may seem like a lot of overhead, a carefully designed symbol registry will result in many varints using only 4 bits (1+3) and ultimately create higher density than byte-oriented encodings like LEB128.

Keeping the description bits together reduces branching (higher performance on modern pipelined CPUs) as the first byte can map to a 256 value lookup table and decode multiple varints at once. It also makes the varints self-synchronizing (similar to UTF-8 but with fewer bits of overhead) meaning they can be scanned backwards.

## Core structure

A series of varint symbols composes a root Item. An Item is a single symbol or a Scope containing Items thus forming a tree structure. A stream contains exactly one Item. Any bits after the final value that completes the root Item must be zero. The first block of a stream must begin with a zero description bit. This ensures a stream can be nested by concatenating at the block level and any padding at the end of the first stream will not be decoded as a distinct Item.

A few symbols consume the next varint as a parameter or have specific rules for how many Items they consume to form a Scope. Having these special rules in the spec for the most common symbols helps increase density. In the interest of forward compatible parsers, once the spec is solidified, no more special rules will be added. Symbols will continue to be added to the registry, but they must only compose within existing symbol semantics.

The [`bind`](./registry/specs/bind.md), [`type_choice`](./registry/specs/type_choice.md), [`type_map`](./registry/specs/type_map.md),  [`type_array`](./registry/specs/type_array.md) symbols compose to form packing descriptions of complex data types. The packing semantics allow parsing to continue without each value being preceded by its type. This achieves high density in many scenarios, such as an array of objects with the same fields and types. See the [registry](./registry/README.md) for specific rules.

The packing descriptions can utilize varints, whole blocks or exact bit widths inside blocks. When whole blocks are mixed with varint blocks, the whole blocks appear after a completed varint block, meaning the logical values may seem out of order in the bit stream, but the corresponding decoding rules can be implemented gracefully. This adds some complexity to the encoder to buffer writes appropriately, but it is justified to avoid wasted padding to the next 32-bit boundary.

Packed values with fixed bit widths are also buffered to appear only after a completed varint block. If a partial fixed width block remains when the next varint is read, the remaining bits are discarded. 

## Text

Unicode code points are represented as varints instead of UTF-8. Packing descriptions determine when to use a special unicode symbol list instead of the default symbol list. Varint blocks are self-synchronizing like UTF-8 but use less bits overall. The ASCII range of unicode is remapped to provide higher density based on frequency of use. See the [registry](./registry/README.md) for more detail.