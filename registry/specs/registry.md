## registry

ID: 31

Classifies a number as a DBUF symbol registry id.

Used to represent symbol ids above the max value of a varint or symbols that have parsing rules.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Symbol id 2 | `0x019f42` | (([type_map](./type_map.md) [registry](./registry.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>"type_choice"</pre> |