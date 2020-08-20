# If

If executes or evaluates a part of code according to the condition.

TODO pattern matching

## If Statement

If statements conditionally executes the body. If the condition is `true`, the body is executed, otherwise, it is skipped. It can have `else` in which the body is executed when the condition isn't `true`.

```stick
if goal >= 100:
    println("you won!")

if goal >= 100:
    println("you won!")
else:
    println("better luck next time")
```

It can be chained with either `else if` or `elif`.

## If Expression

If expression evaluates an expression according to the condition. It have less flexible syntax, `else` part is mandatory and each body can only be a single expression.

```stick
let abs = if num >= 0 (num) else (-num)
```

If expression can be chained with `else if` or `elif` as long as there's `else` in the last.

```stick
let sign = if num > 0 (1) elif num == 0 (0) else (-1)

-- multiline
let sign = if num > 0 (1)
elif num == 0 (0)
else (-1)

-- another multiline
let sign = if num > 0:
    1
elif num == 0:
    0
else:
    -1
```
