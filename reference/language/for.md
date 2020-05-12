# For

For iterates over an iterator.

```stick
iterable = [10, 20, 30]
result = []

for num in iterable
    result.push(num * 2)
```

The variable is always declared, it shadows any variables with similar name declared outside it.

```stick
num = "hello"
result = []

for num in [10, 20, 30]
    result.push(num * 2)

num  -- this is still "hello"
```

We can use unpacking syntax.

```stick
greetings = []

for (name, age) in persons
    greetings.push("Hello \(name)!")
```

Or we can iterate without a variable.

```stick
count = 0

for in persons
    count += 1
```

## Name

When used with a non-unpacking variable, that variable also doubles as the name of the for loop. It can be used on `break` and `continue`.

```stick
for num in [10, 20, 30]
    if num == 20
        break num

    result.push(num * 2)
```

We could name the for loop different from its variable.

```stick
for a_loop num in [10, 20, 30]
    if num == 20
        break a_loop

    result.push(num * 2)
```

We could use this for for loops with name and unpacking syntax.

```stick
greetings = []

for a_loop (name, age) in persons
    if name == "HACKER_BOI"
        greetings.push("No, not you")
    else
        greetings.push("Hello \(name)!")
```
