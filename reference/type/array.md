# Array

Array types are enclosed by square brackets `[]`. It have two optional arguments that constraints element type and length.

```stick
[]
[;]
[Num]
[Num; 20]
[; 20]
```

## Element Type

The first argument constraints the type of the element. It defaults to empty type `()` when omitted.

```stick
[Str]  -- array of strings
[Int]  -- array of integers
[[Str]]  -- array of array of strings
[]  -- array of ()
```

## Length

The second argument constraints the length of the array, it can be any numeric type as long as its integral and non-negative. It defaults to `UInt` or `i[=0..]` when omitted.

```stick
[Str]
[Str;]
-- above are similar to
[Str; UInt]

[Str; 0]  -- empty array
[Str; 10]
[Str; i[=10..20]]
[Str; 10 | 20 | 30]
```
