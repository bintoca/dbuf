## back_reference

- Consumes next varint as distance
- Zero based, a distance of zero means the first eligible Item closest to the current position
- Eligible Items include:
  - Items in function Scopes
  - Eligible Items in a parent text Scope according to text [`back_reference`](../text.md) rules
- Supports chaining, a back reference to a back reference propagates the original Item
- A distance that extends past all eligible Items throws [`error_invalid_back_reference`](error_invalid_back_reference.md) 