## nonexistent

ID: 17

Used as a placeholder for sparse arrays and optional map keys.

When used as a value in a key/value pair of a [type_map](./type_map.md), it is equivalent to the key being absent from that entity. If an empty value that preserves the key's presence is desired, use [describe_no_value](./describe_no_value.md) instead.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Sparse array | `0x1219142540` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) [nonexistent](./nonexistent.md) [parse_varint](./parse_varint.md))) (array (choice 0) (choice 1 5))) | <pre>[null,5]</pre> |
| Map with optional key | `0x019521919400` | (([type_map](./type_map.md) [value](./value.md) ([type_choice](./type_choice.md) [nonexistent](./nonexistent.md) [true](./true.md))) (map (choice 0))) | <pre>{}</pre> |