## registry_symbol_not_accepted_as_array_type

ID: 67

Symbol for validation errors caused by a specific registry symbol during parsing of array types.

Specifications may limit accepted registry symbols to reduce parser complexity and resource usage.

A related stream position includes the bits of the offending symbol.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Error stating a symbol is not accepted at bit position 12</td><td>0x02a0c044c04348c0</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./error.md">error</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./stream_position.md">stream_position</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./registry_symbol_not_accepted_as_array_type.md">registry_symbol_not_accepted_as_array_type</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;12<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "error": "registry_symbol_not_accepted_as_array_type",
  "stream_position": 12
}</pre></td></table>