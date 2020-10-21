# Function Call

Function call or invocation executes the code inside the function. It is an expression and/or statement depending on the voidness and [effect](../type/effect.md) of the function.

```stick
sum(numbers: [10, 20])
```

## Names and Optionality

Each argument have names and it can be omitted. when omitted, it will use the order of the parameter.

```stick
fn power (base: Num, exponent: Num) => base ** exponent

power(10, 4)
-- all same as
power(base: 10, exponent: 4)
```

When the variable is used as an argument without a name, the variable name will be used as a name.

```stick
base = 10
exponent = 4

power(base, exponent)
power(exponent, base)
-- all same as
power(base: base, exponent: exponent)
```

TODO cases where named and unnamed arguments are mixed.

When calling a variadic function, explicit names are not allowed, in this case, variable name isn't considered as name.

## Statement or Expression

Function call is only a statement when the function is void and it is only an expression when the function have [effect](../type/effect.md).
