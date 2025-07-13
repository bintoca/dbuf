## IEEE_754_binary64

ID: 25

Classifies a number as floating point with IEEE 754 binary64 format.

Used in a map with one key and a value type of [parse_varint](./parse_varint.md) or [parse_bit_size](./parse_bit_size.md)

If the size of the number is less than 64 bits, the bits are interpreted as the most significant bits of the IEEE 754 binary64 format.

If the size of the number is greater than 64 bits, the least significant 64 bits (according to the bit order of the stream) are regarded as the value and remaining bits must be ignored.

The S-expression examples show the unsigned integer value.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Floating point with value 1</td><td>0x01994c7fe0</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary64.md">IEEE_754_binary64</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2046<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>1</pre></td>
<tr><td>Floating point with value -1</td><td>0x019958bbff</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary64.md">IEEE_754_binary64</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 12<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3071<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-1</pre></td>
<tr><td>Floating point with value 1 little endian</td><td>0x90206538ff03</td><td>(little_endian_marker <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary64.md">IEEE_754_binary64</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2046<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>1</pre></td>
<tr><td>Floating point with value -1 little endian</td><td>0x902065daf2bf</td><td>(little_endian_marker <br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./IEEE_754_binary64.md">IEEE_754_binary64</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 12<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3071<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>-1</pre></td></table>