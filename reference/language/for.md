# For

For iterates over an iterator.

```stick
let iterable = [10, 20, 30]
let result = []

for num in iterable:
    result.push(num * 2)
```

We can use unpacking syntax. This implicitly declares variables, think of it like it have hidden `let` in it.

```stick
let greetings = []

for (name, age) in persons:
    greetings.push("Hello \(name)!")
```

Or we can iterate without an iteration variable.

```stick
let count = 0

for persons:
    count += 1
```

## Label

When used with a non-unpacking iteration variable, that variable also doubles as the label of the for loop. It can be used on `break` and `continue`.

```stick
for num in [10, 20, 30]:
    if num == 20:
        break num

    result.push(num * 2)
```
