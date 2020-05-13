# Implicit Generic

Stick implements implicit genericity on every parameters.

```stick
fn add(a: Num, b: Num)
    => a + b
```

The example above evaltuates to below.

```stick
<a A: Num, b B: Num>
fn add(a: A, b: B)
    => a + b
```
