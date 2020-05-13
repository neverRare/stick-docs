# Variable

Unlike many other typed programming languages, a variable can have any type, unless when constraint type is defined.

```stick
let foo = true
foo = 100  -- still valid
```

## Constraint Type

Variable holds 2 separate types:

- Immediate type
- Constraint type

Immediate type are implicit type given by its value, it can change on every assignment.

Constraint type provides constraint to immediate types. It is optional and when defined, it should be defined once and before or along the first assignment.

```stick
let foo: Int
foo = false  -- Error
```

Definition of constraint type and assigment can be written in a single statement.

```stick
let foo: Bool = false
```
