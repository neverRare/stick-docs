# File

File is an expression that includes file as indicated by the path and evaluates to string.

The path is relative to the containing module, if it is absolute, it is relative to root folder of the project (the one that directly contains `stick_config.toml`).

```stick
let hello = file "./hello.txt"
```

## Include as bytes

We can alternatively use `bytefile` which then evaluate as an array of bytes (`[UIntX<8>]` or `[i[0..255]]`).

```stick
let hello_byte = bytefile "./hello.txt"
```
