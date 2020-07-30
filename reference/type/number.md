# Number

Stick uses ranges to define numeric types along with union.

## Literal

Number literal can be used as type which will evaluate to a set with the number as the element. You can use this with type union.

```stick
0 | 1 | 2
```

## range

ranges are used to define discrete set of integers or continuous set of numbers (floats) at certain limits. It starts with a letter indicating whether it's discrete `i` or continuous `f`. Limits are preceeded by `=` if it is inclusive. range can extend to infinity, this is done simply by ommiting the limit.

```stick
i[=10..20]
i[=0..]
f[-1..1]
f[..]
```

Note that any side can't both be inclusive and extend to infinity. `i[=..=]` is disallowed.

Stick internally trims both non-integral limit and exclusive limit of discrete range.

```stick
i[=10..20]  -- evaluates to i[=10..=19]
i[=0.5..]  -- evaluates to i[=1..]
```

### Nesting

Numeric types can be used as the limit itself. This includes range and number union.

```stick
f[=f[=0..10]..20]  -- evaluates to f[=0..20]
f[f[=0..10]..20]  -- evaluates to f[=10..20]

i[=0..=5 | 10]  -- evaluates to i[=0..=10]
i[=0..5 | 10]  -- evaluates to i[=0..5] then to i[=0..=4]
```

## Operation

TODO

## Compatibility

TODO

## Predefined Type Alias

```stick
type Num = f[..]
type Int = i[..]
type UInt = i[=0..]

<size S: Single & i[0..]>
type IntX = i[=-(2 ** (S - 1))..2 ** (S - 1)]

<size S: Single & i[0..]>
type UIntX = i[=0..2 ** S]

-- these have internal implementation
type Floor<num: Num>
type Ceil<num: Num>
```
