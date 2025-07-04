## minute

ID: 83

Unit of time equal to 60 seconds or 1/60th of an hour.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Duration of 2 minutes | `0x01c05342` | (([type_map](./type_map.md) [minute](./minute.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>{"minute":2}</pre> |
| Duration of 2 minutes | `0x01c04c01c05342` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [minute](./minute.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"duration":{"minute":2}}</pre> |
| Instant 2 minutes after the start of an hour | `0x01c04a01c05342` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [minute](./minute.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"instant":{"minute":2}}</pre> |
| Interval from 2 to 3 minutes after the start of an hour | `0x01c04b01c05342` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [minute](./minute.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"implied_interval":{"minute":2}}</pre> |