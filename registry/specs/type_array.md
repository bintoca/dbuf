## type_array

ID: 1

Defines a collection.

Consumes one symbol defining the type of the array.

When encountered in the parsing of a data component: Consumes one varint specifying the length of the array. If the array type has data component parsing rules, they are executed for each item.

Implementations must take care not to allocate resources proportional to the length of the array when the array type does not consume additional bits. This represents attack surface where malicious data could specify a very large array length to cause denial of service.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of unsigned integers | `0x142340` | (([type_array](./type_array.md) [parse_varint](./parse_varint.md)) (array 3 4)) | <pre>[3,4]</pre> |