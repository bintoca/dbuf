## end_scope

- Completes a variable length Scope.
- Zero length Scopes are invalid and throw [`error_empty_scope`](error_empty_scope.md)
- If it appears in a fixed length Scope throw [`error_invalid_end_scope`](error_invalid_end_scope.md)
- Can be used to end the root Scope before the end of a bit stream.