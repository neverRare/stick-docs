# Label

Labels are applicable on loop statements such as `for`, `while`, and `loop`. It is often helpful when using `break` or `continue` on deeply nested.

```stick
filtered_fruits = []

fancy_loop:
for fruit in ["apple", "banana", "cherry"]:
    if fruit == "apple":
        continue fancy_loop
    filtered_fruits.push(fruit)
```
