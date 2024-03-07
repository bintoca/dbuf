## Node Type: Choice

Represents a concrete array as the parse result of a [type_choice](../specs/type_choice.md)

Used for clarity in examples of [parse_type](../specs/parse_type.md)

### S-expression format
```
(choice 0 1)
```

The first item after "choice" is the index into the [type_choice](../specs/type_choice.md) list of options.

The second item is the data parsed with the selected option.