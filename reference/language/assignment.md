# Assignment

Assignment is a statement that assigns the value of variable or property based on the value of expression. Keep note that assignment cannot be used as expression.

```stick
foo = 10
foo = 20
```

You can also use either `=` or `:=`.

## Multiple Assignment

Multiple assignment can be condensed to a single statement. All values are evaluated first before assigning it to corresponding variables, this makes swapping of values possible in a single statement.

```stick
foo, bar = 10, 20
-- similar to
foo = 10
bar = 20

-- swapping of values
foo, bar = bar, foo
```

Multiple assignment can be harder to track especially when the expression is huge. It is recommended only use it when swapping values.

## Left to Right Assignment and Chained Assignment

Left to Right (or ltr) assignment are essentially reversed. It can be a used for more concise chained assignment, since it can be broken down into separate lines.

```stick
10 =: foo
20 =: foo

10 + 20 =: sum =: result
-- the same as this
sum = result = 10 + 20

-- multiline
10 + 20
=: sum
=: result
```

Unlike other languages, assignment is not an expression, chained assignment is part of the syntax.
