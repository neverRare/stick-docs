# Skip

Skip is a steady statement.

```stick
__skip { STATEMENTS }
```

## Description

The compiler doesn't statically analyses any statements inside it, it just needs to be syntactically valid.

```stick
let name: Str
__skip {
    num = 420  -- still valid
}
```
