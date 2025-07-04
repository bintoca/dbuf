## copyable

ID: 33

Signifies a nested entity may be repeated later in the DBUF stream.

The sequence of copyable entities form a logical buffer that can be referenced by [copy_distance](./copy_distance.md) and [object Object]

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Copying 3 values, skipping non-copyable values. | `0x122401a1401a245493505880` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) [parse_varint](./parse_varint.md) ([type_map](./type_map.md) [copyable](./copyable.md) [parse_varint](./parse_varint.md)) ([type_map](./type_map.md) [copy_length](./copy_length.md) [parse_varint](./parse_varint.md)))) (array (choice 1 (map 2)) (choice 1 (map 3)) (choice 1 (map 4)) (choice 0 5) (choice 2 (map 2)))) | <pre>[2,3,4,5,4,4,4]</pre> |
| Copy 4 values | `0x12101a1402a3a244410c9130` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) ([type_map](./type_map.md) [copyable](./copyable.md) [parse_varint](./parse_varint.md)) ([type_map](./type_map.md) [copy_distance](./copy_distance.md) [copy_length](./copy_length.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md)))) (array (choice 0 (map 2)) (choice 0 (map 3)) (choice 0 (map 4)) (choice 1 (map 1 3)))) | <pre>[2,3,4,3,4,3,4]</pre> |