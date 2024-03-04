## nonexistent

ID: 0

Used as a placeholder for sparse arrays and optional map keys.

When used as a value in a key/value pair of a [type_map](./type_map.md), it is equivalent to the key being absent from that entity. If an empty value that maintains the keys presence is desired, use [no_value_descriptor](./no_value_descriptor.md) instead.

### Examples

Sparse array: ([type_array](./type_array.md) ([type_choice](./type_choice.md) [nonexistent](./nonexistent.md) [parse_varint](./parse_varint.md)))

Map with optional key: ([type_map](./type_map.md) [id](./id.md) ([type_choice](./type_choice.md) [nonexistent](./nonexistent.md) [true](./true.md)))