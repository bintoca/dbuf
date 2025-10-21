## error

ID: 32

Used as a key in a map to identify error information.

[error](./error.md) must be the first key in a map with more than one key.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Internal error</td><td>0x01a0c040</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./error.md">error</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./error_internal.md">error_internal</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "error": "error_internal"
}</pre></td></table>