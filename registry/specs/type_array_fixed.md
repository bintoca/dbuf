## type_array_fixed

ID: 9

Defines a collection with a fixed length.

Consumes one varint specifying the length and one symbol defining the type of the array.

When encountered in the parsing of a data component: If the array type has data component parsing rules, they are executed for each item.

Implementations must take care not to allocate resources proportional to the length of the array when the array type does not consume additional bits. This represents attack surface where malicious data could specify a very large array length to cause denial of service.

### Examples

<table><tr><th>Description</th><th>Binary</th><th>S-expression</th><th>Unpacked</th></tr><tr><td>Array of unsigned integers</td><td>0x892432</td><td>(<br>&nbsp;&nbsp;&nbsp;(<a href="./type_array_fixed.md">type_array_fixed</a> 2 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="./parse_varint.md">parse_varint</a><br>&nbsp;&nbsp;&nbsp;) <br>&nbsp;&nbsp;&nbsp;(array_fixed <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2<br>&nbsp;&nbsp;&nbsp;)<br>)</td><td><pre>[
  3,
  2
]</pre></td></table>