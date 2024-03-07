# DBUF Codec

DBUF is structured as a stream of binary integers. The first few values in a stream correspond to symbols in the [Registry](./registry/README.md) that describe the size and meaning of values later in the stream.

## Varints

Several areas of the DBUF spec refer to a default variable length integer encoding or "varint" for short. The following bit patterns specify the 5 possible bit widths:

- Leading bit 0 - 3 data bits
- Leading bits 10 - 6 data bits 
- Leading bits 110 - 13 data bits 
- Leading bits 1110 - 20 data bits 
- Leading bits 1111 - 32 data bits

The leading bits may be the most or least significant bits as defined by [little_endian_marker](./registry/specs/little_endian_marker.md) at the beginning of the stream. Likewise, the data bits will follow the same convention of most or least significant first.

## Beginning of a stream

The first 4 bytes may contain the magic number 0xDFDFDFDF. This value is unique among publicly known magic numbers and will not collide with any valid unicode encoding. It is also the same as two consecutive instances of the most significant bit encoding of [magic_number](./registry/specs/magic_number.md) so it will not collide with any valid DBUF data. Any other occurences of [magic_number](./registry/specs/magic_number.md) are treated as a normal symbol without special semantics.

The first byte (or fifth byte if the 4 byte magic number was present) may contain the value 0x91. The presence of this value indicates a bit order of least significant bit first. The absence of this value indicates a bit order of most significant bit first. 0x91 is the most significant bit encoding of [little_endian_marker](./registry/specs/little_endian_marker.md) so it will not collide with any valid DBUF data. Any other occurences of [little_endian_marker](./registry/specs/little_endian_marker.md) are treated as a normal symbol without special semantics.

## Initial Structure

After the optional symbols mentioned above, the structure of a DBUF stream follows the semantics of the [parse_type](./registry/specs/parse_type.md) symbol's type and data components. The literal [parse_type](./registry/specs/parse_type.md) symbol is implicit and omitted from the beginning of the stream. The first value will be a varint encoded symbol starting the type component of the [parse_type](./registry/specs/parse_type.md). The end of the [parse_type](./registry/specs/parse_type.md) data component is considered the end of the DBUF stream. Any data in the bit stream after this point MUST be ignored. A DBUF stream contains exactly one [parse_type](./registry/specs/parse_type.md) structure, never a sequence of structures. If a sequence is desired, the data should be defined as as such inside the single [parse_type](./registry/specs/parse_type.md).

## Symbols that affect parsing

- [type_choice](./registry/specs/type_choice.md)
- [type_map](./registry/specs/type_map.md) 
- [type_array](./registry/specs/type_array.md)
- [parse_varint](./registry/specs/parse_varint.md)
- [parse_bit_size](./registry/specs/parse_bit_size.md)
- [utf8](./registry/specs/utf8.md)
- [parse_type](./registry/specs/parse_type.md)
- [type_choice_shared](./registry/specs/type_choice_shared.md)
- [type_choice_select](./registry/specs/type_choice_select.md)
- [type_map_columns](./registry/specs/type_map_columns.md)
- [type_array_bit](./registry/specs/type_array_bit.md)
- [type_array_fixed](./registry/specs/type_array_fixed.md)
- [parse_any](./registry/specs/parse_any.md)
- [parse_align](./registry/specs/parse_align.md)
- [parse_stream](./registry/specs/parse_stream.md)

All other symbols only represent their literal value and do not create any additional parsing.

### Parse Modes

The specifications of several symbols refer to parse modes:

- any - Consumes one varint representing a registry symbol and sets it's associated parse mode
- choice - Consumes the least number of bits that can represent the number of options in the corresponding [type_choice](./registry/specs/type_choice.md). 
The value consumed is a zero based index into the options and sets the parse mode of the selected option. If the index is outside the bounds of the last option, 
the last option is selected.

## Type Conventions

The order of [type_map](./registry/specs/type_map.md) keys in meaningful and must be maintained across transformations. 

For use cases where a nominal type is desired, the first [type_map](./registry/specs/type_map.md) key should identify the type.