## magic_number

ID: 8159

Placeholder symbol to avoid collisions with the magic number optional prefix at the beginning of a stream.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Stream with prefix</td><td>0xdfdfdfdf019542</td><td>(magic_number_prefix <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "value": 2
}</pre></td>
<tr><td>Normal symbol usage</td><td>0x0195dfdf</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./magic_number.md">magic_number</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "value": "magic_number"
}</pre></td></table>