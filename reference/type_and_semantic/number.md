# Number

Stick uses ranges to define numeric types along with union.

## Literal

Number literal can be used as type which will evaluate to a set with the number as the element. You can use this with type union.

```stick
0 | 1 | 2
```

## Range

TODO explain this syntax

```stick
i[10.<20]
i[0..]
f[-1><1]
f[..]
```

Stick internally trims both non-integral limit and exclusive limit of discrete range.

```stick
i[10.<20]  -- evaluates to i[10..19]
i[0.5..]  -- evaluates to i[1..]
```

### Nesting

Numeric types can be used as the limit itself. This includes range and number union.

```stick
f[f[0.<10]><20]  -- evaluates to f[0.<20]
f[f[0.<10].<20]  -- evaluates to f[10.<20]

i[0..(5 | 10)]  -- evaluates to i[0..10]
i[0.<(5 | 10)]  -- evaluates to i[0.<5] then to i[0..4]
```

## Operation

TODO

## Compatibility

TODO
