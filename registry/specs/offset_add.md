## offset_add

ID: 39

When used in a map with [value](./value.md) describes a number that must be added to obtain the actual value.

Useful for compressing values in a narrow range.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of numbers near 100 | `0x102a79574c06442230` | (([type_array](./type_array.md) ([type_map](./type_map.md) [offset_add](./offset_add.md) [value](./value.md) ([parse_varint](./parse_varint.md) 100) [parse_varint](./parse_varint.md))) (array (map 2) (map 3))) | <pre>[102,103]</pre> |