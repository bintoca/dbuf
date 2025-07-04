## type_array_bit

ID: 8

Defines a collection where the length has a size expressed in bits.

Consumes one varint specifying the number of bits offset by one (meaning a literal value of zero equals one bit and therefore the lowest number of bits is one) and one symbol defining the type of the array.

When encountered in the parsing of a data component: Consumes the specified number of bits as the length of the array. If the array type has data component parsing rules, they are executed for each item.

Implementations must take care not to allocate resources proportional to the length of the array when the array type does not consume additional bits. This represents attack surface where malicious data could specify a very large array length to cause denial of service.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of unsigned integers | `0x88342320` | (([type_array_bit](./type_array_bit.md) 4 [parse_varint](./parse_varint.md)) (array_bit 3 2)) | <pre>[3,2]</pre> |