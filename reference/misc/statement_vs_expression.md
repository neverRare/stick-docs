# Statement vs Expression

Statement and expression are mutually exclusive, a definition can be a statement, an expression, or both, but not neither. Statement means it can stand alone as a whole single statement, and expression simply means it evaluates to a value.

For example, prefix operation is an expression but not a statement. Solely using it as a statement results in syntax error, and needed to be wrapped in curve bracket `()` in order to be syntactically valid (although, it may yield a warning in linting).

The following are non-exhaustive list of definitions according to whether it is an expression, statement, or both.

Statement only:

- alias
- function declaration
- variable declaration
- namespace
- void function call
- void method call
- assignment
- type alias
- return
- break
- continue
- for loop
- if statement

Expression only:

- unnamed function
- steady function
- steady method call
- prefix method call
- if expression
- from
- variable

Both Statement and Expression:

- grouping
- method call other than prefix
- non-void unsteady function call
- non-void unsteady method call

## Declaration

Declarations are statements that requires an identifier.

- namespace
- variable declaration
- function declaration
- type alias
