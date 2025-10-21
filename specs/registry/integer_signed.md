## integer_signed

ID: 22

Classifies a number as a signed integer.

Used in a map with one key and a value type of [parse_varint](./parse_varint.md) or [parse_bit_size](./parse_bit_size.md)

The bits of the value are interpreted as two's complement format.

The S-expression examples show the unsigned value.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Integer with value -2</td><td>0x019646</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./integer_signed.md">integer_signed</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;6<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-2</pre></td>
<tr><td>Integer with value -3</td><td>0x019658bffd</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./integer_signed.md">integer_signed</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 12<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4093<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-3</pre></td>
<tr><td>Integer with value -2 little endian</td><td>0x902059c8</td><td>(little_endian_marker <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./integer_signed.md">integer_signed</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;6<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-2</pre></td>
<tr><td>Integer with value -3 little endian</td><td>0x902059dad2ff</td><td>(little_endian_marker <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./integer_signed.md">integer_signed</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 12<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4093<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-3</pre></td></table>