## parse_bytes

ID: 15

Symbol for parsing binary data as a sequence of bytes.

When encountered in the parsing of a data component: Consumes one varint specifying the length in bytes, then the number of bytes starting from the next 8-bit alignment.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>3 bytes</td><td>0x8f30010203</td><td>(<br>&nbsp;&nbsp;&nbsp;<a href="./parse_bytes.md">parse_bytes</a> <br>&nbsp;&nbsp;&nbsp;0x010203<br>)</td><td><pre>{
  "0": 1,
  "1": 2,
  "2": 3
}</pre></td></table>