## type_array_chunk

ID: 10

Defines a collection that is separated into chunks. Useful for streaming scenarios where the total length is not known at the start.

Consumes one varint specifying the number of bits representing the chunk length offset by one (meaning a literal value of zero equals one bit and therefore the lowest number of bits is one) and one symbol defining the type of the array.

When encountered in the parsing of a data component: Consumes the specified number of bits as the length of a chunk. If the array type has data component parsing rules, they are executed for each item of the chunk. Repeats the behavior for successive chunks until a chunk length of zero ends the array.

Implementations must take care not to allocate resources proportional to the length of the array when the array type does not consume additional bits. This represents attack surface where malicious data could specify a very large array length to cause denial of service.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of unsigned integers | `0x8a342320` | (([type_array_chunk](./type_array_chunk.md) 4 [parse_varint](./parse_varint.md)) (array_chunk (chunk 3 2) (chunk))) | <pre>[3,2]</pre> |