## parse_type_data_immediate

ID: 7

Defines a parsing context that begins with a type component followed by a data component conforming to that type. The parsing context begins immediately after this symbol.

The semantics are identical to the root structure of a DBUF stream.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Map with its second value defined in the type component | `0x02c04695474430` | (([type_map](./type_map.md) [denominator](./denominator.md) [value](./value.md) [parse_varint](./parse_varint.md) ([parse_varint](./parse_varint.md) 4)) (map 3)) | <pre>{"denominator":3,"value":4}</pre> |