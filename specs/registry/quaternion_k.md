## quaternion_k

ID: 73

Used for the k part of quaternion numbers.

A quaternion number is structured as a map with [quaternion_k](./quaternion_k.md), [quaternion_j](./quaternion_j.md), [complex_i](./complex_i.md) and [value](./value.md) for the real part of the number.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Quaternion number with value 2 + 3i + 4j + 5k</td><td>0x04c049c048c0479544445432</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./quaternion_k.md">quaternion_k</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./quaternion_j.md">quaternion_j</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./complex_i.md">complex_i</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "quaternion_k": 5,
  "quaternion_j": 4,
  "complex_i": 3,
  "value": 2
}</pre></td></table>