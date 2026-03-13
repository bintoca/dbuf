## epoch_seconds_continuous

Registry ID: 10

Packed Encoding ID: 36

Used for specifying an instant in time as the number of SI seconds since January 1st 2018 UTC.

### Packed Encoding Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>January 1st 2018 00:01:20 UTC</td><td>0x01a44c0500</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./epoch_seconds_continuous.md">epoch_seconds_continuous</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;80<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>"2018-01-01T00:01:20.000Z"</pre></td></table>