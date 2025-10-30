## IEEE_754_binary32

ID: 24

Classifies a number as floating point with IEEE 754 binary32 format.

Used in a map with one key and a value type of [parse_varint](./parse_varint.md) or [parse_bit_size](./parse_bit_size.md)

If the size of the number is less than 32 bits, the bits are interpreted as the most significant bits of the IEEE 754 binary32 format.

If the size of the number is greater than 32 bits, the least significant 32 bits (according to the bit order of the stream) are regarded as the value and remaining bits must be ignored.

The S-expression examples show the unsigned integer value.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Floating point with value 1</td><td>0x01984c7f00</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary32.md">IEEE_754_binary32</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2032<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>1</pre></td>
<tr><td>Floating point with value -1</td><td>0x019858bbf8</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary32.md">IEEE_754_binary32</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 12<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3064<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-1</pre></td>
<tr><td>Floating point with value 1 little endian</td><td>0x90206138f803</td><td>(little_endian_marker <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary32.md">IEEE_754_binary32</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2032<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>1</pre></td>
<tr><td>Floating point with value -1 little endian</td><td>0x902061da82bf</td><td>(little_endian_marker <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary32.md">IEEE_754_binary32</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 12<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3064<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-1</pre></td></table>