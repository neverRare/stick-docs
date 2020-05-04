# If

If is either an expression or a statement.

## If Statement

TODO

## If Expression

If expression have less flexible syntax, `else` part is mandatory and each body can only be a single expression.

```stick
if num >= 0 (num) else (-num)
```

If expression can be chained with `else if` or `elif` as long as there's `else` in the last.

```stick
if num > 0 (1) elif num == 0 (0) else (-1)

-- multiline
if num > 0 (1)
elif num == 0 (0)
else (-1)

-- another multiline
if num > 0
    1
elif num == 0
    0
else
    -1
```

If expression can't be used as statement.
