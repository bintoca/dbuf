# DBUF Codec Design Decisions

## Self Describing Data

The cornerstone of collaboration is exchanging data. Various approaches to encoding data have evolved over the years. Most strive for simplicity at the cost of completeness. Differing priorities lead to fragmentation and incompatible semantics. Semantics must also be translated out of band from possibly imprecise specifications leading to further incompatibilities. These difficulties accumulate and hinder cooperation. 

DBUF takes a more integrated approach with composable symbols for describing data structures. A carefully crafted set of baseline symbols form a comprehensive type system. The semantics are layered in a way that simpler implementations can be achieved by only using a subset of the baseline symbols.

The descriptive elements are encoded at the beginning of a data stream. This enables dynamically adaptive systems and semantic compression techniques. For aggressive optimization, protocols can define descriptive elements out of band. This provides the lowest overhead while still benefiting from common semantics. 

## Symbol Registry

In the pursuit of interoperability, there is a clear need to uniquely identify concepts. DBUF accommodates this with a global symbol list. Symbols are encoded as integers but are a distinct data type separate from integers. 

Encoding as integers provides a compact representation even in the most minimal implementations. In contrast, RDF subject and predicate URLs are much larger and typically require another form of compression for practical usage.

Having one global registry creates some centralization but it's an opportunity to create a space to come together and collaborate.

## Customizable Bit Widths

Most binary formats define data in multiples of 8 bits. This is for simplicity of implementations written against the 8-bit load/store instructions of most hardware. The downside of that approach is that values are likely to have unused bits. The lack of adaptability also leads to fragmentation into alternative formats for optimized use cases.

DBUF includes mechanisms to define values of any bit width. While the lack of 8-bit alignment can hinder decoding throughput in the general case, values can be specially composed for optimal throughput. For example, an RGBA pixel format with bit widths of (10, 10, 10, 2) can be natively described in DBUF rather than being a separate out-of-band format.

DBUF also envisions a future where hardware instructions are not solely 8-bit oriented. It should be feasible to define instructions that read an arbitrary number of bits from a bit level pointer. This would alleviate throughput concerns for unaligned data.

## Varints

Variable length integers are a common feature of binary formats, providing compact encodings for smaller integers that tend to occur more often than larger integers. Most formats use 8-bit aligned varints, e.g. base128 with seven data bits and one flag bit.

DBUF has a more aggressive [varint](../specs/codec.md) format that is 4-bit aligned. This is justified by the high rate of occurrence of numbers 0-7 that can then occupy just 4-bits and provide a significant overall gain in density.

4-bit alignment has a slight impact on encoding/decoding speed but can still be optimized enough for most use cases. For maximum optimization, varints only need to be used in descriptive elements, with bulk data having a different preferred alignment. 

The maximum payload of a varint is 32-bits. This predictability allows for optimizations such as eliding length checking in parsers. Larger sizes are supported by composable description with [parse_bit_size](../specs/registry/parse_bit_size.md).

Another long term goal is that the above characteristics make it attractive to create new hardware instructions for varint decoding. Presumably those instructions would be faster than the software implementations of any possible varint format.

## Maps

Descriptions of maps (meaning associative arrays or collections of key/value pairs) are composed with all the keys first, then the data types of all the values, then lastly the values themselves. 

This separation allows for reusable descriptions such as an array of maps that all have the same keys. The keys are not repeated for each map in that case, resulting in semantic compression. 

Having keys and types at the forefront also allows protocols to reject unsupported data without reading an entire dataset. Even more advanced scenarios like JIT compilation based on incoming data types is also possible.

## Arrays

Descriptions of arrays are composable with other symbols to form nestable structures.

There are four array definition symbols each geared to different use cases:

- [type_array](../specs/registry/type_array.md) - Implies a varint encoded array length. Intended for the most compact type definitions.
- [type_array_bit](../specs/registry/type_array_bit.md) - Takes a bit size for the array length. Intended for more precise control of alignment and array lengths above the range of 32-bit integers.
- [type_array_fixed](../specs/registry/type_array_fixed.md) - Takes a fixed size for the array length. Intended for arrays with repetitive lengths such are matrixes.
- [type_array_chunk](../specs/registry/type_array_chunk.md) - Intended for arrays of unknown length such as streaming data. 

## Type Choice

The data types and values in a given dataset are often constrained or have some form of commonality. Programming languages typically address this with enums or union types. DBUF integrates this concept with high composability through the [type_choice](../specs/registry/type_choice.md) symbol.

[type_choice](../specs/registry/type_choice.md) encodes a selection from a set of choices with the minimum number of bits that can represent the total count of choices. For example, a field that has five possible values is encoded as three bits. 

The choice selection can also extend to data types. A field that has integer values from 0-1000 with a high frequency of values less than 16 could encode a choice (occupying 1-bit) between 4-bit and 10-bit values.

Choices can also be nested which can then form the equivalent of Huffman codes. These capabilities enable use cases where the composed semantic compression can outperform external compression schemes. 

[type_choice_shared](../specs/registry/type_choice_shared.md) and [type_choice_select](../specs/registry/type_choice_select.md) provide an additional layer of functionality describing recursive data types and dictionary like compression.

## Type Optional

Fields that may or may not have a value are so common that it justifies a shorthand symbol. [type_optional](../specs/registry/type_optional.md) is semantically equivalent to a [type_choice](../specs/registry/type_choice.md) of [nonexistent](../specs/registry/nonexistent.md) and a given data type.

## Text Strings

With the [parse_text](../specs/registry/parse_text.md) symbol, text is encoded as an array of UTF8 bytes. Since other values in a DBUF stream may not be aligned to 8-bit boundaries, implicit padding bits enforce alignment. The padding can amount to modest overhead for some datasets but is warranted given the optimized copy routines of 8-bit aligned hardware.

Custom text encodings other than UTF8 can be described with the [text](../specs/registry/text.md) symbol attached to more specialized arrays.

## Byte Strings

With the [parse_bytes](../specs/registry/parse_bytes.md) symbol, data is encoded as an array of bytes. Since other values in a DBUF stream may not be aligned to 8-bit boundaries, implicit padding bits enforce alignment. The padding can amount to modest overhead for some datasets but is warranted given the optimized copy routines of 8-bit aligned hardware.

Compressed byte streams can be described with the [bytes](../specs/registry/bytes.md) symbol attached to more specialized arrays.

## Endianness

Since DBUF allows values of any bit width, it is necessary to define the order that bits are consumed from a stream. There is an unfortunate dilemma that most internet protocols use network byte order (big endian) while a large share of current hardware is little endian. For the sake of broad adoption DBUF makes this choice self-describing with the presence or absence of the prefix symbol [little_endian_marker](../specs/registry/little_endian_marker.md). 

DBUF semantics are defined in terms of a series of numeric values, making them identical in either endianness.

## Empty Values

The concept of nothing takes many forms across data formats, programming languages and databases. Some examples are null, undefined, DBNull, nil, None. DBUF symbols describe empty values in a way more suited to structural typing. 

The [nonexistent](../specs/registry/nonexistent.md) symbol is a placeholder for combining heterogeneous sets of data. When used in a map, it implies a key does not exist on that object rather than holding the value nonexistent. 

The [describe_no_value](../specs/registry/describe_no_value.md) symbol is a placeholder that should not be elided in heterogeneous data. When used in a map, the key does exist. It can also be extended to embed another value as a reason why there is no value. 

## Structural Typing

In the interest of having parsing routines that can be separated into logical layers, DBUF has just 16 symbols that form the core parsing rules. More complex data types can be composed as maps that are interpreted as a single logical value rather than a set of key/value pairs. 

Typical patterns are: 
- map with one key that serves to qualify a value
- map with two or three keys that add metadata to a value

## Signed Integers

The [integer_signed](../specs/registry/integer_signed.md) symbol qualifies a value as signed integer. The bits are interpreted as two's complement. This allows data to be exchanged in formats that match hardware layouts without additional decoding.

## Binary Floating Point

IEEE 754 binary has strong hardware support so DBUF uses it's 16, 32, and 64 bit definitions as the main representation of floating point numbers. Composition with customized bit widths enables reduced precision use cases (e.g. a 24-bit value with the exponent bit pattern of binary32).

Values larger that 64-bits can be composed with the [exponent_base2](../specs/registry/exponent_base2.md) symbol.

## Decimal Floating Point

IEEE 754 has a decimal format, but it has little hardware support. The values of decimal fields are more likely to share the same exponent (e.g. two decimal place precision for money). Therefore, better semantic compression can be achieved with composition of the [exponent_base10](../specs/registry/exponent_base10.md) symbol. Values with the same exponent can then be encoded as integers and benefit from the speed of integer math instructions.

## Dates and Time

[epoch_seconds_continuous](../specs/registry/epoch_seconds_continuous.md) is the symbol for representing timestamps. Composing it with DBUF integers and decimals allows it to have any range and precision. The epoch is defined as an offset of TAI (a continuous time scale without leap seconds). This avoids the leap second ambiguities of POSIX time and requires implementations to be leap second aware when converting to UTC. 

The epoch instant was chosen as the equivalent of January 1st 2018 UTC. This places all existing leap seconds before the epoch so datasets with exclusively positive values could elide leap second conversions. A future leap second would disrupt that optimization but standards bodies have preliminary agreements to eliminate leap seconds by 2035. The current trend of UT1-UTC difference indicates another leap second is unlikely before 2035.

Timestamps in the future can't necessarily be represented with integers. Changes in legal definitions like daylight savings time can affect the meaning of future timestamps in relation to the past. A structure with the components of civil time is needed to retain the intended meaning. DBUF includes symbols for year, month, day, etc. for this purpose. 