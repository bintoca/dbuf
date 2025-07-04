## duration

ID: 76

Used for describing a nested entity as a duration of time.

If the nested entity is only composed of seconds, the seconds are considered continuous similar to the TAI time scale.

If the nested entity is composed of other time elements, the duration may have to consider the semantics of calendars.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Duration of 2 seconds | `0x01c04c01c05442` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [second](./second.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"duration":{"second":2}}</pre> |
| Duration of one month and 2 seconds | `0x01c04c02c050c0544412` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [month](./month.md) [second](./second.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md))) (map (map 1 2))) | <pre>{"duration":{"month":1,"second":2}}</pre> |