## IEEE_754_binary16

ID: 23

Classifies a number as floating point with IEEE 754 binary16 format.

Used in a map with one key and a value type of [parse_varint](./parse_varint.md) or [parse_bit_size](./parse_bit_size.md)

If the size of the number is less than 16 bits, the bits are interpreted as the most significant bits of the IEEE 754 binary16 format.

If the size of the number is greater than 16 bits, the least significant 16 bits (according to the bit order of the stream) are regarded as the value and remaining bits must be ignored.

The S-expression examples show the unsigned integer value.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Floating point with value 1 | `0x01974c7800` | (([type_map](./type_map.md) [IEEE_754_binary16](./IEEE_754_binary16.md) [parse_varint](./parse_varint.md)) (map 1920)) | <pre>1</pre> |
| Floating point with value -1 | `0x019758bbc0` | (([type_map](./type_map.md) [IEEE_754_binary16](./IEEE_754_binary16.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 3008)) | <pre>-1</pre> |
| Floating point with value 1 little endian | `0x90205d38c003` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [IEEE_754_binary16](./IEEE_754_binary16.md) [parse_varint](./parse_varint.md)) (map 1920)) | <pre>1</pre> |
| Floating point with value -1 little endian | `0x90205dda02bc` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [IEEE_754_binary16](./IEEE_754_binary16.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 3008)) | <pre>-1</pre> |
| Floating point with value -1 oversized | `0x01975930bc00` | (([type_map](./type_map.md) [IEEE_754_binary16](./IEEE_754_binary16.md) ([parse_bit_size](./parse_bit_size.md) 20)) (map 48128)) | <pre>-1</pre> |
| Floating point with value -1 oversized little endian | `0x90205dda04c00b` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [IEEE_754_binary16](./IEEE_754_binary16.md) ([parse_bit_size](./parse_bit_size.md) 20)) (map 48128)) | <pre>-1</pre> |