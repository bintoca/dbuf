## copy_length

ID: 34

Specifies a count of values to copy from the [copyable](./copyable.md) buffer of a stream.

Nested value must be an unsigned integer.

Count is offset by one.

Copying begins from the most recent[copyable](./copyable.md) item.

Copied values are also appended to the [copyable](./copyable.md) buffer.

Can be composed with [copy_distance](./copy_distance.md) for copying a range of values.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Copying 3 values, skipping non-copyable values. | `0x122401a1401a245493505880` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) [parse_varint](./parse_varint.md) ([type_map](./type_map.md) [copyable](./copyable.md) [parse_varint](./parse_varint.md)) ([type_map](./type_map.md) [copy_length](./copy_length.md) [parse_varint](./parse_varint.md)))) (array (choice 1 (map 2)) (choice 1 (map 3)) (choice 1 (map 4)) (choice 0 5) (choice 2 (map 2)))) | <pre>[2,3,4,5,4,4,4]</pre> |
| Copy 4 values | `0x12101a1402a3a244410c9130` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) ([type_map](./type_map.md) [copyable](./copyable.md) [parse_varint](./parse_varint.md)) ([type_map](./type_map.md) [copy_distance](./copy_distance.md) [copy_length](./copy_length.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md)))) (array (choice 0 (map 2)) (choice 0 (map 3)) (choice 0 (map 4)) (choice 1 (map 1 3)))) | <pre>[2,3,4,3,4,3,4]</pre> |