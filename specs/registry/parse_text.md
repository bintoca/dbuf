## parse_text

ID: 6

Symbol for parsing text as a string of UTF8 bytes.

When encountered in the parsing of a data component: Consumes one varint specifying the length in bytes, then the number of bytes starting from the next 8-bit alignment.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>String of text</td><td>0x68b068656c6c6f20776f726c64</td><td>(<br>&nbsp;&nbsp;&nbsp;<a href="./parse_text.md">parse_text</a> <br>&nbsp;&nbsp;&nbsp;0x68656c6c6f20776f726c64<br>)</td><td><pre>"hello world"</pre></td></table>