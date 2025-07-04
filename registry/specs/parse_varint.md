## parse_varint

ID: 4

Unsigned integer type with varint encoding.

When encountered in the parsing of a data component: Consumes one varint.

Can be used as a base type for other kinds of numbers such as signed integers and floats.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of unsigned integers | `0x142340` | (([type_array](./type_array.md) [parse_varint](./parse_varint.md)) (array 3 4)) | <pre>[3,4]</pre> |
| Array of signed integers | `0x1019642340` | (([type_array](./type_array.md) ([type_map](./type_map.md) [integer_signed](./integer_signed.md) [parse_varint](./parse_varint.md))) (array (map 3) (map 4))) | <pre>[3,-4]</pre> |