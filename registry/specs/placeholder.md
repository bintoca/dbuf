## placeholder

- Similar to null in other languages, except if it appears as a value of a field in a structural type it implies that field does not exist rather than the field holding a null value.
- Typical usage will be as part of a [`type_choice`](type_choice.md) where structural types with slightly different fields can be packed in the same collection.
- If it is the last Item in a stream (in order to pad the end to a 32-bit boundary) it is ignored by the root Scope.