## start

ID: 77

Used for describing a nested entity as an instant that begins an interval.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Start January 1st 2019</td><td>0x01c04d01c04f41</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./start.md">start</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./year.md">year</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "start": {
    "year": 1
  }
}</pre></td></table>