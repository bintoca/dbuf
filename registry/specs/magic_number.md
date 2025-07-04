## magic_number

ID: 8159

Placeholder symbol to avoid collisions with the magic number optional prefix at the beginning of a stream.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Stream with prefix | `0xdfdfdfdf019542` | ([magic_number](./magic_number.md) [magic_number](./magic_number.md) ([type_map](./type_map.md) [value](./value.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>{"value":2}</pre> |
| Normal symbol usage | `0x0195dfdf` | (([type_map](./type_map.md) [value](./value.md) [magic_number](./magic_number.md)) (map)) | <pre>{"value":"magic_number"}</pre> |