# Tagged Structs

Tagged structs are first class values that can handle compounded data (combination of fields, like strcuts) associated with a "tag". This tag is used to differentiate from other tagged structs that can contain different associated fields.

You can initiate it just like a struct but with additional syntax for tag.

```stick
let movement = @move(x: 10, y: 20)
let movement = @rotate(deg: 30)
```

Moreover, if there's only one field, you can omit the field name. If there's none, you can omit the parenthesis.

```stick
let movement = @rotate(30)
```

## Accessing and matching

You can access its field with `.`, however, the tag must be known before doing so. You can use `match` statement for it.

```stick
match movement:
    @move:
        let x = movement.x
        let y = movement.y
        -- do things
    @rotate:
        let deg = movement.deg
        -- do things
```

Or access its values directly with more advance pattern.

```stick
match movement:
    @move(let x, let y):
        -- do things
    @rotate(let deg):
        -- do things
```
