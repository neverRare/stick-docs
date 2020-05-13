# Generator

Generators are special function that returns a value and can be reentered later.

```stick
gn range(min: Int, max: Int)
    num = min
    while num < max
        => num
        num += 1
```

Generators evaluates to a function that returns an iterator. Generators can only be steady and there's no way to comunicate back once it is called.
