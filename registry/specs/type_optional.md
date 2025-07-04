## type_optional

ID: 3

Defines a choice of two options with the first option implied as [nonexistent](./nonexistent.md)

Consumes one symbol defining the second option.

When encountered in the parsing of a data component: Consumes one bit as the selected choice.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Sparse array | `0x134254` | (([type_array](./type_array.md) ([type_optional](./type_optional.md) [parse_varint](./parse_varint.md))) (array (choice 0) (choice 1 5))) | <pre>[null,5]</pre> |
| Map with optional key | `0x01953940` | (([type_map](./type_map.md) [value](./value.md) ([type_optional](./type_optional.md) [true](./true.md))) (map (choice 0))) | <pre>{}</pre> |