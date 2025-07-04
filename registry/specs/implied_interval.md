## implied_interval

ID: 75

Used for describing a nested entity as an interval in a singluar way instead of a start and end.

The boundary sementics are inclusive at the start, exclusive at the end. (E.g. 2019-01-01T00:00:00 <= [Interval of year 2019] < 2020-01-01T00:00:00)

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Interval from 2 to 3 seconds after the start of a minute | `0x01c04b01c05442` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [second](./second.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"implied_interval":{"second":2}}</pre> |
| Interval of year 2019 | `0x01c04b01c04f41` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [year](./year.md) [parse_varint](./parse_varint.md))) (map (map 1))) | <pre>{"implied_interval":{"year":1}}</pre> |