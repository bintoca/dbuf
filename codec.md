# DBUF Codec

DBUF is structured as a stream of binary integers. The first few values in a stream correspond to symbols in the [Registry](./registry/README.md) that describe the size and meaning of values later in the stream. The symbols also compose in ways that can describe nested or repeating patterns with dense packing.

## Varints

Several areas of the DBUF spec refer to a default variable length integer encoding or "varint" for short. The following bit patterns specify the 5 possible bit widths:

- Leading bit 0 - 3 data bits
- Leading bits 10 - 6 data bits
- Leading bits 110 - 13 data bits
- Leading bits 1110 - 20 data bits
- Leading bits 1111 - 32 data bits


The leading bits may be the most or least significant bits as defined by the optional prefixes at the beginning of the stream. Likewise, the data bits will follow the same convention of most or least significant first.

## Optional Prefixes

The first 4 bytes of a stream may contain the magic number 0xDFDFDFDF. This value is unique among publicly known magic numbers and will not collide with any valid unicode encoding. It is also the same as two consecutive instances of the most significant bit encoding of [magic_number](./registry/specs/magic_number.md) so it will not collide with any valid DBUF data. Any other occurences of [magic_number](./registry/specs/magic_number.md) are treated as a normal symbol without special semantics.

The first byte (or fifth byte if the 4 byte magic number was present) may contain the value 0x90. The presence of this value indicates a bit order of least significant bit first. The absence of this value indicates a bit order of most significant bit first. 0x90 is the most significant bit encoding of [little_endian_marker](./registry/specs/little_endian_marker.md) so it will not collide with any valid DBUF data. Any other occurences of [little_endian_marker](./registry/specs/little_endian_marker.md) are treated as a normal symbol without special semantics.

## Root Structure

After the optional prefixes, a DBUF stream consists of two parts, a type component that defines a structure and a data component with data that conforms to the type component.

Some symbols consume additional bits and/or additional symbols which create nested structures. The type component consists of one symbol and its nested children. The data component begins directly after, following the rules of the root symbol of the type component.

The end of the data component is considered the end of the DBUF stream. Any data in the bit stream after this point MUST be ignored. A DBUF stream contains exactly one type component and one data component, never a sequence of type/data components. If a sequence is desired, the type component should use an appropriate structure such as [type_array](./registry/specs/type_array.md)

## Symbols with unique parsing rules

- [type_map](./registry/specs/type_map.md)
- [type_array](./registry/specs/type_array.md)
- [type_choice](./registry/specs/type_choice.md)
- [type_optional](./registry/specs/type_optional.md)
- [parse_varint](./registry/specs/parse_varint.md)
- [parse_bit_size](./registry/specs/parse_bit_size.md)
- [parse_text](./registry/specs/parse_text.md)
- [parse_type_data_immediate](./registry/specs/parse_type_data_immediate.md)
- [type_array_bit](./registry/specs/type_array_bit.md)
- [type_array_fixed](./registry/specs/type_array_fixed.md)
- [type_array_chunk](./registry/specs/type_array_chunk.md)
- [type_choice_shared](./registry/specs/type_choice_shared.md)
- [type_choice_select](./registry/specs/type_choice_select.md)
- [parse_align](./registry/specs/parse_align.md)
- [parse_type_data](./registry/specs/parse_type_data.md)
- [parse_bytes](./registry/specs/parse_bytes.md)
