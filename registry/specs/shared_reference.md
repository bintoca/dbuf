## shared_reference

- Consumes next varint as distance
- Zero based, a distance of zero means the first eligible Item closest to the current position
- Eligible Items include:
  - Items marked with [`shared`](shared.md) inside the current Item of a function or root Scope
- A distance that extends past all eligible Items throws [`error_invalid_shared_reference`](error_invalid_shared_reference.md) 