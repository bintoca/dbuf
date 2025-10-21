## hour

ID: 82

Unit of time equal to 60 minutes or 1/24th of a day.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Duration of 2 hours</td><td>0x01c05242</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./hour.md">hour</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "hour": 2
}</pre></td>
<tr><td>Duration of 2 hours</td><td>0x01c04c01c05242</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./duration.md">duration</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./hour.md">hour</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "duration": {
    "hour": 2
  }
}</pre></td>
<tr><td>Instant 2 hours after the start of a day</td><td>0x01c04a01c05242</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./instant.md">instant</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./hour.md">hour</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "instant": {
    "hour": 2
  }
}</pre></td>
<tr><td>Interval from 2 to 3 hours after the start of a day</td><td>0x01c04b01c05242</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./implied_interval.md">implied_interval</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./hour.md">hour</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "implied_interval": {
    "hour": 2
  }
}</pre></td></table>