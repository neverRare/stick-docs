# Enum

Enum is an enumerated type that also can be used as tagged union of structs.

```stick
Action = enum
    Move(x: Num, y: Num)
    Speak(: Str)
    Quit
```
