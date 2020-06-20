# String Literals

String literals are used for defining string. It is enclosed by `"`.

```stick
"Hello, World!"
""  -- empty string
```

## Escape notation

| Escape notation        | Output           |
| ---------------------- | ---------------- |
| `\"`                   | double quotation |
| `\\`                   | backslash        |
| `\n`                   | new line         |
| `\r`                   | catridge return  |
| `\t`                   | tab              |
| `\v`                   | vertical tab     |
| `\b`                   | backspace        |
| `\f`                   | form feed        |
| `\u{XX}`               | UTF-8 code unit  |
| `\uXXXX` or `\u{XXXX}` | UTF-16 code unit |
| `\u{XXXXXXXX}`         | UTF-32 code unit |

## Raw String

Strings can be alternatively enclosed with `'`, unlike double quoted strings, these do not have escape notation. This kind of string can be referred to as raw string.

You can use a number of `#` around it, it will be delimited with a matching number of `#` and `'`.

```stick
'raw string'
#'raw string'#
##'raw string'##
```

## Multiline

Strings syntaxes defined above can't contain line terminators. Theres another syntax that can span multiple lines. This works for regular string and raw string.

```stick
"""
multiline
string
"""
```

The starting `"""` or `'''` must be directly preceded by indentation (or line terminator) and followed by a line terminator. It matches the next matching `"""` or `'''` with the same indentation. It cleanly trims indentation inside so it aligns with `"""`, so the following declaration.

```stick
let python_code =
    """
    def add(a, b):
        return a + b

    """
```

is the same as

```stick
let python_code = "def add(a, b):\n    return a + b\n"
```

TODO explain how line terminators is parsed, does CRLF remains CRLF, or is it converted to LF.
