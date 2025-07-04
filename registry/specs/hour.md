## hour

ID: 82

Unit of time equal to 60 minutes or 1/24th of a day.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Duration of 2 hours | `0x01c05242` | (([type_map](./type_map.md) [hour](./hour.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>{"hour":2}</pre> |
| Duration of 2 hours | `0x01c04c01c05242` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [hour](./hour.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"duration":{"hour":2}}</pre> |
| Instant 2 hours after the start of a day | `0x01c04a01c05242` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [hour](./hour.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"instant":{"hour":2}}</pre> |
| Interval from 2 to 3 hours after the start of a day | `0x01c04b01c05242` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [hour](./hour.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"implied_interval":{"hour":2}}</pre> |