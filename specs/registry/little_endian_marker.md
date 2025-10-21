## little_endian_marker

ID: 16

Placeholder symbol to avoid collisions with the bit order optional prefix at the beginning of a stream.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Stream with prefix</td><td>0x9020330268</td><td>(little_endian_marker <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "denominator": 3
}</pre></td>
<tr><td>Normal symbol usage</td><td>0x01c04690</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./little_endian_marker.md">little_endian_marker</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "denominator": "little_endian_marker"
}</pre></td></table>