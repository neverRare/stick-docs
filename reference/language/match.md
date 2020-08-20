# Match

Match control flow can be a statement or an expression. It conditionally executes or evaluates a part of code according to a value's pattern.

## Match statement

TODO explanation

```stick
match name:
    @some let name:
        println("username found: " + name)

    @none:
        println("username not found")
```

Alternative syntax.

```stick
match name
case @some let name:
    println("username found: " + name)

case @none:
    println("username not found")
```

## Match expression

TODO explanation

```stick
let score = match score:
    @some let score => score + 10
    @none => 0
```
