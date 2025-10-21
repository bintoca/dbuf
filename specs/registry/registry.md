## registry

ID: 31

Classifies a number as a DBUF symbol registry id.

Used to represent symbol ids above the max value of a varint or symbols that have parsing rules.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Symbol id 2</td><td>0x019f42</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./registry.md">registry</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>"type_choice"</pre></td></table>