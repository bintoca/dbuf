## day

ID: 81

Unit of time equal to 24 hours or one rotation of the earth.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Duration of 2 days | `0x01c05142` | (([type_map](./type_map.md) [day](./day.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>{"day":2}</pre> |
| Duration of 2 days | `0x01c04c01c05142` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [day](./day.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"duration":{"day":2}}</pre> |
| Instant 2 days after the start of a month | `0x01c04a01c05142` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [day](./day.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"instant":{"day":2}}</pre> |
| Interval from 2 to 3 days after the start of a month | `0x01c04b01c05142` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [day](./day.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"implied_interval":{"day":2}}</pre> |