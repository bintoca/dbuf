## prefix

ID: 42

Used for compression of strings that begin with the same substring.

When used in a map with [value](./value.md) the unpacked value is a concatenation of the bytes of prefix and value

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>String "world" with prefix "hello "</td><td>0x02aa95666068656c6c6f2050776f726c64</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./prefix.md">prefix</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x68656c6c6f20 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x776f726c64<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>"hello world"</pre></td></table>