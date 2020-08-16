# Method Call

Method call have similar syntax to function call and property access, but it can have simplified syntax.

```stick
car.repaint(color: "white")
```

When the method only have 1 non-self parameter, the curve bracket `()` can be omitted. With this form, the name should also be omitted.

```stick
car .repaint "white"
```

## Prefix Notation

The syntax above are infix. methods with only self parameter can have prefix syntax.

```stick
.accelerate car
-- similar to
car.accelerate()
```

Keep in mind that prefix method calls are not statements.

## Symbolic Methods

Symbolic methods are simply method with symbolic name.

## Precedence

Stick doesn't have well defined precedence, this include property access.
