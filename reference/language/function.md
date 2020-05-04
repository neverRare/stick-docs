# Function

Function is an expression used to define scoped snippet of code that are executed when the function is called. It can have inputs called parameters and return or output a value.

This section only refers to defining functions.

```stick
sum = fn (numbers: [Num])
    total = 0
    for num in numbers
        total += num

    => total
```

## Defining as statement

Functions is generally an expression. In the example above, the function is defined and assigned to a variable `sum`. It can be rewritten as below, which is functionally the same.

```stick
fn sum(numbers: [Num])
    total = 0
    for num in numbers
        total += num

    => total
```

This form of function can't be used as expression.

## Rest Parameter

Rest parameter allow us to represent indefinite number of parameters as an array, all arguments would be unlabelled. There can't be other parameter when using this format.

```stick
fn sum(..numbers: [Str])
    total = 0
    for num in numbers
        total += num

    => total
```

We recommend using array instead of rest parameter as possible.

## Returning a value

In the example above, `=> total` is the return statement, which gives values for its calls. You can use the maybe more familiar `return` instead of the fancy `=>`.

```stick
sum = fn (numbers: [Num])
    total = 0
    for num in numbers
        total += num

    return total
```

Return statement can also acts as early exit.

```stick
fibonacci = fn (num: UInt) -> UInt
    if num <= 1
        => num

    => fibonacci(num - 1) + fibonacci(num - 2)
```

### Lambda

The body can contain only return statement. Such function can have further simplified syntax. This is commonly referred to as lambda expression.

```stick
square = fn (num: Num) => num * num
```

### Void Function

Functions can be a void and will not return any value. It's calls can't be used as an expression.

```stick
counter: UInt = 0

increment = fn ()   counter += 1
```

Only unsteady function can be void, which is further explained at [steadiness of function](../type/steadiness.md).

## Anonymous Function

Often times, when using function anonymously, such as when passing it as an argument, its parameter already have inferred types. In this case, type annotations can be omitted.

## Accessing outside values

Functions are also closure, it can access and reassign some values outside it, but with few restrictions: only values with constrainted type and values that are assigned once can be read, and only values with constrainted type can be reassigned.

### Mutating the parameter
