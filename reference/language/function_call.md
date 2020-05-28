# Function Call

Function call or invocation executes the code inside the function. It is an expression and/or statement depending on the voidiness and [steadiness](../type/steadiness.md) of the function.

```stick
sum(numbers: [10, 20])
```

## Labels and Omittability

Each argument have labels. It can be omitted by either ommiting the label and the colon `:` or by leaving the colon in place. This will use the order of the parameter.

```stick
fn power (base: Num, exponent: Num) => base ** exponent

power(10, 4)
power(:10, :4)
-- all same as
power(base: 10, exponent: 4)
```

When the variable is used as an argument without a label, the variable name will be used as a label. To truly use unlabelled arguement, prefix it with `:`.

```stick
base = 10
exponent = 4

power(base, exponent)
power(exponent, base)
-- all same as
power(base: base, exponent: exponent)

power(:exponent, :base)
-- same as
power(base: exponent, exponent: base)
```

The whole arguments can only be either fully unlabelled or fully labelled. We can't mix unlabelled and labelled arguments.

When calling a variadic function, explicit labels are not allowed, in this case, variable name isn't considered as label.

## Statement or Expression

Function call is only a statement when the function is void and it is only an expression when the function is [steady](../type/steadiness.md).
