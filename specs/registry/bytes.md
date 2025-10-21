## bytes

ID: 29

Used to describe a nested entity as bytes.

Semantically equivalent to [parse_bytes](./parse_bytes.md) but provides more flexibility in encoding options.

If the nested entity is an array of non-negative integers less than 256, it is interpreted as a sequence bytes.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Bytes as array of integers</td><td>0x019d143c051c052c0530</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./bytes.md">bytes</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_array.md">type_array</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(array <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;81 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;82 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;83<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "0": 81,
  "1": 82,
  "2": 83
}</pre></td></table>