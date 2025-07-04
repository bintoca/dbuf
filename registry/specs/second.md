## second

ID: 84

SI unit of time.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Duration of 2 seconds | `0x01c05442` | (([type_map](./type_map.md) [second](./second.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>{"second":2}</pre> |
| Duration of 2 seconds | `0x01c04c01c05442` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [second](./second.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"duration":{"second":2}}</pre> |
| Instant 2 seconds after the start of a minute | `0x01c04a01c05442` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [second](./second.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"instant":{"second":2}}</pre> |
| Interval from 2 to 3 seconds after the start of a minute | `0x01c04b01c05442` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [second](./second.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"implied_interval":{"second":2}}</pre> |