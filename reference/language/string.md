# String Literals

String literals are used for defining string instances. It is enclosed by `'` or `'''`, referred to as single quoted strings.

```stick
'Hello, World!'
'''Hello, World!'''
''  -- empty string
```

This however have limitations:

- If enclosed by `'` it can't contain `'`
- If enclosed by `'''` it can't contain `'''`
- It can't contain newlines

Strings can be alternatively enclosed with `"` or `"""`, referred to as double quoted strings. Unlike single quoted strings, these have escape notation to alleviate these limitations.

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

Keep note that single quoted strings don't have escape notation, it can freely use `\`.

## String interpolation

Double quoted strings can also interpolate via `\`.

```stick
name = "World"
"Hello, \(name)!"
```
