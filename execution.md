# DBUF Execution

A DBUF stream may act as an executable set of instructions sent between a client and server. By default, execution begins with the last Item in the root Scope. If the last Item is [`placeholder`](./registry/specs/placeholder.md), it begins with the second to last Item.

For situations where execution should begin before reading to the end of a stream, such as uploading a large data value, an operation may be tagged with the [`execute_early`](./registry/specs/execute_early.md) symbol. Tagging occurs using a [`bind`](./registry/specs/bind.md) with the first Item being the tag.

For bi-directional stream connections, a return value from execution is sent to the client. A server may alternatively return error information by tagging it with the [`error`](./registry/specs/error.md) symbol.

## Functions
Coming Soon