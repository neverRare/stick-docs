# Skip

Skip is used to ignore some part of the code on runtime and on static analysis.

```stick
let name: Str

skip
    print("Bye")  -- this doesn't get printed
    num = 42  -- still valid
```

This is similar to multi-line comments in other languages, but the body needs to be a syntactically valid code.
