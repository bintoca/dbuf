# DBUF Execution

For bi-directional stream connections, a return value from execution is sent to the client. A server may alternatively return error information by tagging it with the [`error`](./registry/specs/error.md) symbol. Tagging occurs using a [`bind`](./registry/specs/bind.md) with the first Item being the tag.

## Functions
Coming Soon