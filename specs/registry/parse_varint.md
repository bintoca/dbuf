## parse_varint

ID: 4

Unsigned integer type with varint encoding.

When encountered in the parsing of a data component: Consumes one varint.

Can be used as a base type for other kinds of numbers such as signed integers and floats.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Array of unsigned integers</td><td>0x142340</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_array.md">type_array</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(array <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>[
  3,
  4
]</pre></td>
<tr><td>Array of signed integers</td><td>0x1019642340</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_array.md">type_array</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./integer_signed.md">integer_signed</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(array <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>[
  3,
  -4
]</pre></td></table>