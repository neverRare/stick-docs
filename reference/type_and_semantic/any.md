# Any

Type Any represents all types: any types is compatible with this type. This is the default constraint for generic type parameter.

```stick
<T>  -- T is constrained to Any, this is similar to <T: Any>
fn wrap_in_array(x: T):
    => [x]
```

As described in [implicit generic](./implicit_generic.md), this can be rewritten to the following.

```stick
fn wrap_in_array(x: Any):
    => [x]
```
