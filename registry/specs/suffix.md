## suffix

ID: 43

Used for compression of strings that end with the same substring.

When used in a map with [value](./value.md) the unpacked value is a concatenation of the bytes of value and suffix

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>String "hello " with suffix "world"</td><td>0x0295ab666068656c6c6f2050776f726c64</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./suffix.md">suffix</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x68656c6c6f20 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x776f726c64<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>"hello world"</pre></td>
<tr><td>String "wo" with prefix "hello " and suffix "rld"</td><td>0x03aa95ab666668656c6c6f2020776f30726c64</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./prefix.md">prefix</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./suffix.md">suffix</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x68656c6c6f20 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x776f <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x726c64<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>"hello world"</pre></td></table>