# String Literals

String literals are used for defining string. It is enclosed by `"`.

```stick
"Hello, World!"
""  -- empty string
```

## Escape notation

| Escape notation            | Output           |
| -------------------------- | ---------------- |
| `\"`                       | double quotation |
| `\\`                       | backslash        |
| `\n`                       | new line         |
| `\r`                       | carriage return  |
| `\t`                       | tab              |
| `\v`                       | vertical tab     |
| `\b`                       | backspace        |
| `\f`                       | form feed        |
| `\xXX`                     | UTF-8 code unit  |
| `\uXXXX`                   | UTF-16 code unit |
| `\u{X}` ... `\u{XXXXXXXX}` | UTF-32 code unit |

## Raw String

Strings can be alternatively enclosed with `'`, unlike double quoted strings, these do not have escape notation. This kind of string can be referred to as raw string.

You can use a number of `#` around it, it will be delimited with a matching number of `#` and `'`.

```stick
'raw string'
#'raw string'#
##'raw string'##
```

## Multiline

Strings syntaxes defined above can't contain line breaks. Theres another syntax that can span multiple lines. This only works for regular string.

```stick
"""
multiline
string
"""
```

The starting `"""` must be directly preceded by indentation (or line break) and followed by a line break. It matches the next `"""` with the same indentation. It cleanly trims indentation inside so it aligns with `"""`, so the following declaration.

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

Stick recognize LF and CRLF as line breaks and they are translated as LF.
