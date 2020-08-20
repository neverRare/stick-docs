# Tag

You can tag any kind of value. This is used to create tagged union.

```stick
let movement = match input:
    "move" => @move(x: 10, y: 20)
    "rotate" => @rotate 30
    "jump" => @jump
```

You can access the value normally like an untagged value. But the tag must be known before doing so.

```stick
if @move = movement:
    let x = movement.x
    let y = movement.y
```
