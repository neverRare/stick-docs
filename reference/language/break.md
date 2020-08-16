# Break

`break` is a statement that terminates a statement, particularly a function or a loop statement. When given no keyword or label, it terminates the nearest containing function or loop.

```stick
-- some errors aside

fn very_loopy_function(array: []):
    for i in array:
        while true:
            loop:
                break while  -- this terminates `while`
                break i  -- this terminates a loop statement with label `i`
                break  -- this terminates `loop`

```

You can't use break to a loop when there is a nearer containing function.

```stick
loop
    fn foo()
        break loop -- error

```
