## format

ID: 41

Describes a data format.

When used in a map with [value](./value.md) describes the format of that value.

If the format value is a fixed bit width unsigned integer or an array of fixed bit width unsigned integers, the bits are interpreted as the type component of a distinct DBUF stream. Any associated [value](./value.md) is interpeted as the data component of a DBUF stream.

If the format value is the [format](./format.md) symbol, the format is a complete DBUF stream.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Format for a DBUF type_array of varints</td><td>0x01a98f1014</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./format.md">format</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_bytes.md">parse_bytes</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x14<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "format": {
    "0": 20
  }
}</pre></td>
<tr><td>Format for a DBUF type_array of varints with array of varints (1,2,3) packed as bytes</td><td>0x02a9958f8f1014203123</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./format.md">format</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_bytes.md">parse_bytes</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_bytes.md">parse_bytes</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x14 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x3123<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "format": {
    "0": 20
  },
  "value": {
    "0": 49,
    "1": 35
  }
}</pre></td>
<tr><td>Format for a DBUF stream</td><td>0x01a9a9</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./format.md">format</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./format.md">format</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "format": "format"
}</pre></td>
<tr><td>Format for a DBUF stream with type and array of varints (1,2,3) packed as bytes</td><td>0x02a995a98f30143123</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./format.md">format</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./format.md">format</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_bytes.md">parse_bytes</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0x143123<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "format": "format",
  "value": {
    "0": 20,
    "1": 49,
    "2": 35
  }
}</pre></td></table>