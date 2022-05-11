## forward_reference

- Consumes next varint as distance
- Zero based, a distance of zero means the first eligible Item closest to the current position
- Only Items in the current Scope are eligible
- Supports chaining, a forward reference to a back/forward reference propagates the original Item
- A distance that extends past the end of the current Scope throws [`error_invalid_forward_reference`](error_invalid_forward_reference.md)
- Recursion caused to a forward reference may throw [`error_max_forward_depth`](error_max_forward_depth.md)