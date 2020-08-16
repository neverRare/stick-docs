# Continue

Continue is a statement that terminates the block of statement then continues to the next iteration of the loop statement. When given no keyword or label, it terminates the nearest containing loop.

```stick
-- some errors aside

fn very_loopy_function(array: []):
    for i in array:
        while true:
            loop:
                continue while  -- this applies to `while`
                continue i  -- this applies to a loop statement with label `i`
                continue  -- this applies to `loop`

```

You can't use continue to a loop when there is a nearer containing function.

```stick
loop
    fn foo()
        continue  -- error

```
