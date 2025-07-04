## integer_signed

ID: 22

Classifies a number as a signed integer.

Used in a map with one key and a value type of [parse_varint](./parse_varint.md) or [parse_bit_size](./parse_bit_size.md)

The bits of the value are interpreted as two's complement format.

The S-expression examples show the unsigned value.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Integer with value -2 | `0x019646` | (([type_map](./type_map.md) [integer_signed](./integer_signed.md) [parse_varint](./parse_varint.md)) (map 6)) | <pre>-2</pre> |
| Integer with value -3 | `0x019658bffd` | (([type_map](./type_map.md) [integer_signed](./integer_signed.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 4093)) | <pre>-3</pre> |
| Integer with value -2 little endian | `0x902059c8` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [integer_signed](./integer_signed.md) [parse_varint](./parse_varint.md)) (map 6)) | <pre>-2</pre> |
| Integer with value -3 little endian | `0x902059dad2ff` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [integer_signed](./integer_signed.md) ([parse_bit_size](./parse_bit_size.md) 12)) (map 4093)) | <pre>-3</pre> |