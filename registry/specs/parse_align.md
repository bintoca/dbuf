## parse_align

ID: 13

Defines an instruction to align the parser to a multiple of bits.

Consumes one varint specifying the power of two number of bits, offset by one. (E.g. 0 = 2 bits, 1 = 4 bits, 2 = 8 bits, etc). Then consumes one symbol defining the nested type.

When encountered in the parsing of a data component: Consumes the least number of bits that bring the parser into the specified alignment. Then executes any data component parsing rules of the nested type.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Align to 32 bits before parsing varint</td><td>0x8d44000050</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./parse_align.md">parse_align</a> 32 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(align <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>5</pre></td></table>