# Function

## Parameter Type

Type annotation for parameter are required unless already inferred by outside typings.

```stick
```

## Generic

## Return Type

The type annotation are usually optional, return type are usually inferred.

```stick
-- inferred to `UInt`, no need for annotation
add_uint = fn (a: UInt, b: UInt)
    => a + b
```

Explicit return type usually just constraints the inferred return type.

```stick
-- even with `Num`, the return type is still `UInt`
add_uint = fn (a: UInt, b: UInt) -> Num
    => a + b
```

Explicit return type is required for some cases when return type can't be inferred precisely, one is when using recursion.

When functions are called, the return type is deduced even further. This is due to [implicit generic](implicit_generic.md).

```stick
add = fn(a: i[=1 < 5], b: i[=1 < 10])
    => add_uint(a, b)  -- this is inferred to i[=2 < =13] instead of UInt
```
