## text

ID: 28

Used to describe a nested entity as text.

Semantically equivalent to [parse_text](./parse_text.md) but provides more flexibility in encoding options.

If the nested entity is an array of non-negative integers less than 256, it is interpreted as a string of UTF8 bytes.

If the nested entity is a single non-negative integer, it is interpreted as a Unicode code point.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Text as array of integers corresponding to UTF8 bytes | `0x019c143c051c052c0530` | (([type_map](./type_map.md) [text](./text.md) ([type_array](./type_array.md) [parse_varint](./parse_varint.md))) (map (array 81 82 83))) | <pre>"QRS"</pre> |
| Single integer corresponding to unicode code point | `0x019c4e1f6010` | (([type_map](./type_map.md) [text](./text.md) [parse_varint](./parse_varint.md)) (map 128513)) | <pre>"😁"</pre> |