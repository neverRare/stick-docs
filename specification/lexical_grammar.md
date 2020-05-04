# Lexical Grammar

Stick have simple lexical grammar and left the burden at parser.

## Whitespace

Stick recognizes all characters with whitespace unicode property excluding line feed `\n` and carriage return `\r` as whitespace. However, for pythonic indentation, space `\u0020` and tab `\t` are only valid and they can't be mixed.

## Line Terminators

Stick recognizes `\r\n`, `\n` and `\r` as a single line terminator.

## Comment

Comments start with two hyphens `--` and ends with a line terminator (not included) or end of file (EOF). It can contain any characters excluding line terminator, since it will terminate the comment.

## Literals

### Number

A number literal can have underscore, and it is pretty permissive.

### String

## Identifier

Any string of undercore `_` and characters with letter and number unicode property is recognized as identifier. It can't start with a digit `0-9`

## Operator

Any string of characters with punctuation and symbol unicode property excluding underscore `_` is recognized as operator.
