## IEEE_754_binary32

ID: 24

Classifies a number as floating point with IEEE 754 binary32 format.

Used in a map with one key and a value type of [parse_varint](./parse_varint.md) or [parse_bit_size](./parse_bit_size.md)

If the size of the number is less than 32 bits, the bits are interpreted as the most significant bits of the IEEE 754 binary32 format.

If the size of the number is greater than 32 bits, the least significant 32 bits (according to the bit order of the stream) are regarded as the value and remaining bits must be ignored.

The S-expression examples show the unsigned integer value.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Floating point with value 1 | `0x01984c7f00` | (([type_map](./type_map.md) [IEEE_754_binary32](./IEEE_754_binary32.md) [parse_varint](./parse_varint.md)) (map 2032)) | <pre>1</pre> |
| Floating point with value -1 | `0x019858bbf8` | (([type_map](./type_map.md) [IEEE_754_binary32](./IEEE_754_binary32.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 3064)) | <pre>-1</pre> |
| Floating point with value 1 little endian | `0x90206138f803` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [IEEE_754_binary32](./IEEE_754_binary32.md) [parse_varint](./parse_varint.md)) (map 2032)) | <pre>1</pre> |
| Floating point with value -1 little endian | `0x902061da82bf` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [IEEE_754_binary32](./IEEE_754_binary32.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 3064)) | <pre>-1</pre> |