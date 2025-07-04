## instant

ID: 74

Used for describing a nested entity as an instant in time.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Instant 2 seconds after the start of a minute | `0x01c04a01c05442` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [second](./second.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"instant":{"second":2}}</pre> |
| Instant January 1st 2038 without timezone | `0x01c04a01c04f4940` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [year](./year.md) [parse_varint](./parse_varint.md))) (map (map 20))) | <pre>"2038-01-01T08:00:00.000Z"</pre> |