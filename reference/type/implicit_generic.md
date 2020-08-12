# Implicit Generic

Stick implements implicit generic on every parameters.

```stick
fn add(a: Num, b: Num):
    => a + b
```

The example above evaluates to below.

```stick
<a A: Num, b B: Num>
fn add(a: A, b: B):
    => a + b
```
