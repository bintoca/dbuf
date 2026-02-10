## exponent_base10

ID: 27

Used for the exponent of decimal floating point numbers with arbitrary range and precision.

If used as the only key in a map, or structured in a map only with [sign](./sign.md) the value is interpreted with a base10 exponent of -2

If structured in a map with [value](./value.md) the value is the base10 exponent offset by 7

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Decimal floating point with value 1.01 with single key</td><td>0x019b5765</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./exponent_base10.md">exponent_base10</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 8<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;101<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>1.01</pre></td>
<tr><td>Decimal floating point with value 1.01 with two keys</td><td>0x029b95457565</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./exponent_base10.md">exponent_base10</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_bit_size.md">parse_bit_size</a> 8<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;101<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>1.01</pre></td></table>