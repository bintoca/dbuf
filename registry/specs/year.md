## year

ID: 79

Unit of time according to the Gregorian calendar.

For instants and intervals a value of zero (meaning the epoch) is the year 2018

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Duration of 2 years | `0x01c04f42` | (([type_map](./type_map.md) [year](./year.md) [parse_varint](./parse_varint.md)) (map 2)) | <pre>{"year":2}</pre> |
| Duration of 2 years | `0x01c04c01c04f42` | (([type_map](./type_map.md) [duration](./duration.md) ([type_map](./type_map.md) [year](./year.md) [parse_varint](./parse_varint.md))) (map (map 2))) | <pre>{"duration":{"year":2}}</pre> |
| Instant January 1st 2038 without timezone | `0x01c04a01c04f4940` | (([type_map](./type_map.md) [instant](./instant.md) ([type_map](./type_map.md) [year](./year.md) [parse_varint](./parse_varint.md))) (map (map 20))) | <pre>"2038-01-01T08:00:00.000Z"</pre> |
| Interval of year 2019 | `0x01c04b01c04f41` | (([type_map](./type_map.md) [implied_interval](./implied_interval.md) ([type_map](./type_map.md) [year](./year.md) [parse_varint](./parse_varint.md))) (map (map 1))) | <pre>{"implied_interval":{"year":1}}</pre> |