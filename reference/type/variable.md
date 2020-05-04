# Variable

Unlike many other typed programming languages, a variable can have any type, unless when constraint type is defined.

```stick
foo = true
foo = 100  -- still valid
```

## Constraint Type

Variable holds 2 separate types:

- Immediate type
- Constraint type

Immediate type are implicit type given by its value, it can change on every assignment.

Constraint type provides constraint to immediate types. It is optional and when defined, it should be defined once and before or along the first assignment.

```stick
foo: Int
foo = false  -- Error
```

Definition of constraint type and assigment can be written in a single statement.

```stick
foo: Bool = false
```

## Implicit Constraint Type

Constraint types can be defined implicitly and use the first immediate type as the constraint type. Such variable can't be initialized without value. However, keep in mind that Stick always tries to deduce set of possible values as the immediate type.

```stick
foo := 10  -- have constraint type of {10} instead of Int

foo = 10  -- just fine
foo = 20  -- Error
```
