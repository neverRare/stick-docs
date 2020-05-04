# Variable

Variable holds a value.

```stick
foo = 300
bar = "Hello"
```

## Declaration and Assignment

Through assignment, a variable can be declared or change its value.

```stick
foo = 68  -- declare foo with 68
foo = 42  -- now change it to 42
```

## Explicit Declaration

Variables can be declared explicitly with `let` keyword. This provides flexibility and enables unitialized variable and shadowing.

```stick
let foo = 30
```

Explicit declaration also works as well for unpacking and chained assignment.

```stick
-- chained assignment
100
=: let result
=: people.score

-- unpacking
joe =: let (name, age)
-- or
joe =: (let name, let age)
```

It doesn't work with multiple assignment however.

```stick
let foo, bar = 10, "baz"  -- syntax error
```
