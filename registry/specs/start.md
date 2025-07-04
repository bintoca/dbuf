## start

ID: 77

Used for describing a nested entity as an instant that begins an interval.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Start January 1st 2019 | `0x01c04d01c04f41` | (([type_map](./type_map.md) [start](./start.md) ([type_map](./type_map.md) [year](./year.md) [parse_varint](./parse_varint.md))) (map (map 1))) | <pre>{"start":{"year":1}}</pre> |