## IEEE_754_binary64

ID: 25

Classifies a number as floating point with IEEE 754 binary64 format.

Used in a map with one key and a value type of [parse_varint](./parse_varint.md) or [parse_bit_size](./parse_bit_size.md)

If the size of the number is less than 64 bits, the bits are interpreted as the most significant bits of the IEEE 754 binary64 format.

If the size of the number is greater than 64 bits, the least significant 64 bits (according to the bit order of the stream) are regarded as the value and remaining bits must be ignored.

The S-expression examples show the unsigned integer value.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Floating point with value 1 | `0x01994c7fe0` | (([type_map](./type_map.md) [IEEE_754_binary64](./IEEE_754_binary64.md) [parse_varint](./parse_varint.md)) (map 2046)) | <pre>1</pre> |
| Floating point with value -1 | `0x019958bbff` | (([type_map](./type_map.md) [IEEE_754_binary64](./IEEE_754_binary64.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 3071)) | <pre>-1</pre> |
| Floating point with value 1 little endian | `0x90206538ff03` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [IEEE_754_binary64](./IEEE_754_binary64.md) [parse_varint](./parse_varint.md)) (map 2046)) | <pre>1</pre> |
| Floating point with value -1 little endian | `0x902065daf2bf` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [IEEE_754_binary64](./IEEE_754_binary64.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 3071)) | <pre>-1</pre> |