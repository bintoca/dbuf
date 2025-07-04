## parse_bit_size

ID: 5

Unsigned integer type with specified width.

Consumes one varint specifying the number of bits offset by one, meaning a literal value of zero equals one bit and therefore the lowest number of bits is one.

When encountered in the parsing of a data component: Consumes the specified number of bits.

Can be used as a base type for other kinds of numbers such as signed integers and floats.

The S-expression examples show the number of bits without an offset.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of unsigned integers | `0x153256` | (([type_array](./type_array.md) ([parse_bit_size](./parse_bit_size.md) 4)) (array 5 6)) | <pre>[5,6]</pre> |
| Array of signed integers | `0x1019653256` | (([type_array](./type_array.md) ([type_map](./type_map.md) [integer_signed](./integer_signed.md) ([parse_bit_size](./parse_bit_size.md) 4))) (array (map 5) (map 6))) | <pre>[5,6]</pre> |