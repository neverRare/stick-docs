# Features

As Stick develops, some of the features here may be changed.

## Opt-in Significant Indentation

Stick would allow either pythonic identation or braces. Notice that the return statement here starts with `=>`.

```stick
-- pythonic
fn sum(numbers: [Num])
    let total = 0
    for num in numbers
       total += num

    => total

-- brace
fn sum(numbers: [Num]) {
    let total = 0
    for num in numbers {
        total += num
    }
    => total
}
```

This could be used with parenthesis `()` such as in function call. Notice the named arguments here.

```stick
let result = power (
    base: 10
    power: 2
)

let result = power
    base: 10
    power: 2
```

There should be no ambuigity. There are simple rules:

- If theres `(` for function call or `{` for control flow, either on the same line or on the next line, then it is braced style, indentation won't matter.
- Otherwise, if there's an increased indent on the next line, then it is pythonic.
- Otherwise, there's have no block at all, for control flow, this is a syntax error.

You may notice this isn't really pythonic, there's no `:` after the `fn (...)`. Should I add it? Also, should I support Ruby style?

## Omittable semicolon and comma

TODO

## Alias

Here's maybe a little controversial feature. Identifiers can be given an alias.

```stick
alias {
    array arr list
}
```

This would work multi-directionally, `array` is an alias to `arr` and `list`, `arr` is also an alias to `array` and `list`, and so on. This doesn't alias directly, it will only work with identifiers imported from library or from standard library, it won't alias identifiers that are immediately declared.

This may cause ambuigity. My recommendation is to keep aliasing at minimum, such as `to_string` can be aliased to `to_str` but not `tos`.

This is maybe good for non-english languages.

## No reserved keywords

Actually, there is, but it starts with two underscore like `__function`. These keywords can be aliased.

```stick
alias {
    fn def __function
}
```

When aliasing a keyword, it will only work at one direction, `fn` is an alias to `__function` but not to `def`.

Crazily enough, keyword aliases can be shadowed by a variable.

```stick
let fn = 10

-- fn is now a variable, this is syntax error
fn stuff() {...}

-- but we could use other alias of function
def stuff() {...}
```

This is a cheaty way of providing forward compatibility for language design.

## Case-convention insensitive

Borrowed from Nim, an identifier would interchange between `snake_case` or `camelCase`, this would only work when it starts with a lowercase character. This might break with abbreviation so we would treat it as a single word instead. For example, `parse_json` or `parseJson` but not `parseJSON`.

## Very narrowed types

Inspired from typescript's `as const`. Types are always narrowed down as possible. Even with operations, it would still be narrowed.

```stick
let foo = 2  -- foo have type `2`
let bar = 3 + foo  -- bar have type `5`
```

Even with annotation, it would still be narrowed.

```stick
let foo: Int = 2  -- foo have type `2`
```

## Seemingly dynamic but actually static

Because values have always have narrowed type, it may not make sense that a variable is constrainted to its first inferred type as what other typed languages does.

```stick
let foo = 20  -- foo have inferred type `20`, its always narrowed
foo = 30
-- if foo is constrainted to its first inferred type
-- this is not possible as 30 is not a subtype of 20
```

So instead, a variable can have any types, it will still be statically typed. This is inspired from rust's variable shadowing, but in stick, it will still be the same variable.

```stick
let foo = 2
-- foo have type `2` from this point

foo = 0.3
-- foo now have type `0.3` from this point

foo = [10, 20]
-- now `[10 | 20; 2]` from this point
```

`[10 | 20; 2]` is array type, `10 | 20` is union of `10` and `20`, and `2` is the length.

This can be problematic with functions (functions are also closure in stick):

```stick
let foo = 10
closure()
foo = 20
closure()
foo = false
closure()

fn closure()
    -- what is the type of foo here?
```

When accessing variable outside the function, it needs to either be a constant (variables that remains unreassigned are inferred as constant), or have type annotation.

```stick
let foo: Int = 10
closure()
foo = 20
closure()
foo = false  -- type error here
closure()

fn closure()
    -- foo is `Int` at this point
```

## Numeric range

Stick have numeric range, a numeric type that defines its minima and maxima, and it can either be integer or float. `=` means inclusive here. This is borrowed from [typescript's requested feature](https://github.com/microsoft/TypeScript/issues/15480).

```stick
i[=10..20]  -- integer from 10 to 19
i[=0..]  -- integer from 0 up to infinity (arbitrarily precise)
f[-1..1]  -- all floats between -1 and 1
f[..]  -- all float numbers

-- stick's float is 64-bit floating point number
```

As mentioned in [Very narrowed types](#very-narrowed-types), operation between numbers with range type would also have result with narrowed type.

```stick
fn foo(bar: i[=0..10], baz: i[=5..10])
    -- bar is narrowed to i[=0..=9]
    -- baz is narrowed to i[=5..=9]
    => bar + baz  -- inferred to i[=5..=18]
```

This could prevent integer overflow, division by zero, and out of bound error.

## Implicit generics

Every parameter would be implicitly generic.

```stick
fn sum(a: Num, b: Num)
    => a + b

-- this becomes
<a A: Num, b B: Num>
fn sum(a: A, b: B)
    => a + b
```

Type parameters would be named. `a A` means it accepts type parameter `a` but renamed `A` on the function.

```stick
sum:<a: Int, b: Int>(...)
```

This could better narrow the types.

```stick
let result = sum(10, 5)
-- this is similar to
result = sum<a: 10, b: 5>(10, 5)
-- the result would be inferred to type 15
```

## Controlled side-effect

Types may also be narrowed with control flows.

```stick
fn do_something(num: Int)
    if num == 0
        -- num should be `0` from this point
```

If we have a function that mutates `num`, we will have a problem.

```stick
fn do_something(num: Int)
    if num == 0
        mutate_num()
        -- num should be `1` from this point, or is it?

    fn mutate_num()
        num += 1
```

To solve this problem, we could either don't let functions mutate outside variables or let function have another sort of metadata that tells which variables are mutated. I'll choose the latter, it seems wackier.

We could have restriction such as functions with side-effect can't be use as high-level function.

## Backend agnostic

Stick is backend agnostic in a way that it doesn't assume any environment or IO. A stick project can choose any backend and import it like a library, or, have no backend at all, so any other project regardless of backend can use and import it.

These backend would be distributed as bytecodes which compiles the code. Being also a library, it could also expose IO functionality and other stuffs.

Stick is also backend agnostic in a way that it doesn't really care about its backend, it doesn't have well-defined memory management. The target code would ideally be garbage-collected and imperative as well.

## Multiple entry

A stick project could have many entry, and each entry could have different backend. There may certain cases this would be useful, for example, for a stick library, it's main entry would have no backend and exposes such functionality, and it may have testing entry with a backend with output, so it could output its result.
