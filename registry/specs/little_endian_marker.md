## little_endian_marker

ID: 16

Placeholder symbol to avoid collisions with the bit order optional prefix at the beginning of a stream.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Stream with prefix | `0x9020330268` | ([little_endian_marker](./little_endian_marker.md) ([type_map](./type_map.md) [denominator](./denominator.md) [parse_varint](./parse_varint.md)) (map 3)) | <pre>{"denominator":3}</pre> |
| Normal symbol usage | `0x01c04690` | (([type_map](./type_map.md) [denominator](./denominator.md) [little_endian_marker](./little_endian_marker.md)) (map)) | <pre>{"denominator":"little_endian_marker"}</pre> |