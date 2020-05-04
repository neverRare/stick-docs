# Implicit Generic

Stick implements implicit genericity on every parameters.

```stick
add = fn (a: Num, b: Num)
    => a + b
```

The example above evaltuates to below.

```stick
<a A: Num, b B: Num>
add = fn (a: A, b: B)
    => a + b
```
