## type_array

ID: 1

Defines a collection.

Consumes one symbol defining the type of the array.

When encountered in the parsing of a data component: Consumes one varint specifying the length of the array. If the array type has data component parsing rules, they are executed for each item.

Implementations must take care not to allocate resources proportional to the length of the array when the array type does not consume additional bits. This represents attack surface where malicious data could specify a very large array length to cause denial of service.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Array of unsigned integers</td><td>0x142340</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_array.md">type_array</a> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(array <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>[
  3,
  4
]</pre></td></table>