## type_array_fixed

ID: 9

Defines a collection with a fixed length.

Consumes one varint specifying the length and one symbol defining the type of the array.

When encountered in the parsing of a data component: If the array type has data component parsing rules, they are executed for each item.

Implementations must take care not to allocate resources proportional to the length of the array when the array type does not consume additional bits. This represents attack surface where malicious data could specify a very large array length to cause denial of service.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of unsigned integers | `0x892432` | (([type_array_fixed](./type_array_fixed.md) 2 [parse_varint](./parse_varint.md)) (array_fixed 3 2)) | <pre>[3,2]</pre> |