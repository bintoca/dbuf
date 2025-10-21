## type_map

ID: 0

Defines a collection of key/value pairs.

Consumes one varint specifying the number of pairs to parse. All the keys come first followed by all the values.

When encountered in the parsing of a data component: Each key or value that has data component parsing rules is executed.

Type component values and data component values combine to form a logical map. If an array of maps all have the same value for a key, that value can be specified once in the type component and omittted in the data component.

If the same key is specified more than once, the unpacking procedure combines the values into an array. If the first value is an array, the following values are appended to the first array. If following values are arrays, they are appended as nested, not flattened into the first array.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Two keys with unsigned integer values</td><td>0x02c046954434</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "denominator": 3,
  "value": 4
}</pre></td>
<tr><td>Array of maps with value in the type component</td><td>0x102c046957424247</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_array.md">type_array</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./parse_type_data_immediate.md">parse_type_data_immediate</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(array <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;7<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;)<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>[
  {
    "denominator": 2,
    "value": 4
  },
  {
    "denominator": 2,
    "value": 7
  }
]</pre></td>
<tr><td>Key specified twice</td><td>0x03c04695c046444345</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "denominator": [
    3,
    5
  ],
  "value": 4
}</pre></td>
<tr><td>Key specified twice with array as first value</td><td>0x03c04695c04614441345</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_map.md">type_map</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./value.md">value</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./denominator.md">denominator</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(<a href="./type_array.md">type_array</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(map <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(array <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>{
  "denominator": [
    3,
    5
  ],
  "value": 4
}</pre></td></table>