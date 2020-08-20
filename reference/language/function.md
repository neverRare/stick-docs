# Function

Function is an expression used to define scoped snippet of code that are executed when the function is called. It can have inputs called parameters and return or output a value.

This section only refers to defining functions.

```stick
fn sum(numbers):
    let total = 0
    for num in numbers:
        total += num

    => total
```

## Function as expression

Functions is generally an expression. However in the example above, it is a statement and not an expression, it is similar to the following

```stick
let sum = fn (numbers):
    let total = 0
    for num in numbers:
        total += num

    => total
```

## Variadic function

Variadic function allow us to represent variable number of parameters as an array, all arguments would be unnamed. There can't be other parameter when using this format.

```stick
fn sum(..numbers):
    let total = 0
    for num in numbers:
        total += num

    => total
```

We recommend using array as parameter instead as possible.

## Returning a value

In the example above, `=> total` is the return statement, which gives values for its calls. You can use the maybe more familiar `return` instead of the fancy `=>`.

Return statement can also acts as early exit.

```stick
fn fibonacci(num):
    if num <= 1:
        => num

    => fibonacci(num - 1) + fibonacci(num - 2)
```

### Lambda

The body can contain only return statement. Such function can have further simplified syntax. This is commonly referred to as lambda expression.

```stick
fn square(num) => num * num
```

### Void Function

Functions can be a void and will not return any value. It's calls can't be used as an expression.

```stick
counter: UInt = 0

fn increment()
    counter += 1
```

Only unsteady function can be void, which is further explained at [steadiness of function](../type/steadiness.md).
