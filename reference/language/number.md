# Number

Number literals defines numeric data.

```stick
10
0.5
1_000_000
```

While it uses underscore `_` for its visual separator, the whole literal and the decimal part after the `.` can't start with `_`.

## E notation

Stick also supports E notation to represent an estimation of large or small number. This is sometimes referred to as scientific notation. You can use either `e` or `E`.

```stick
5.9724_e24
5.9724_e+24
9.109_383_56_e-31
```

In the example, we used `_` as a visual separator between mantissa and abscissa, it can be written as `5.9724e24`. The `_` can't be placed between `e` or `E` and `+` or `-`.

## Base-N

TODO
