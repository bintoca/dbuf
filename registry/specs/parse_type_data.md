## parse_type_data

ID: 14

Defines a parsing context that begins with a type component followed by a data component conforming to that type.

When encountered in the parsing of a data component: Consumes a type and data component with semantics identical to the root structure of a DBUF stream.

Useful for values that can be of any type.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Map with type information not known until the data component | `0x01c0468e43` | (([type_map](./type_map.md) [denominator](./denominator.md) [parse_type_data](./parse_type_data.md)) (map ([parse_varint](./parse_varint.md) 3))) | <pre>{"denominator":3}</pre> |