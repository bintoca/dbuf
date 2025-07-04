## month

ID: 80

Unit of time according to the Gregorian calendar.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Duration of 2 months | `0x01c05042` | (([type_map](./type_map.md) [month](./month.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>{"month":2}</pre> |
| Duration of 2 months | `0x01c04c01c05042` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [month](./month.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"duration":{"month":2}}</pre> |
| Instant 2 months after the start of a year | `0x01c04a01c05042` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [month](./month.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"instant":{"month":2}}</pre> |
| Interval from 2 to 3 months after the start of a year | `0x01c04b01c05042` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [month](./month.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"implied_interval":{"month":2}}</pre> |