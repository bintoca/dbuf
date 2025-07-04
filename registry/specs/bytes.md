## bytes

ID: 29

Used to describe a nested entity as bytes.

Semantically equivalent to [parse_bytes](./parse_bytes.md) but provides more flexibility in encoding options.

If the nested entity is an array of non-negative integers less than 256, it is interpreted as a sequence bytes.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Bytes as array of integers | `0x019d143c051c052c0530` | (([type_map](./type_map.md) [bytes](./bytes.md) ([type_array](./type_array.md) [parse_varint](./parse_varint.md))) (map (array 81 82 83))) | <pre>{"0":81,"1":82,"2":83}</pre> |