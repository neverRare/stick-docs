# Extern

Extern declaration are used to include inline code in different language. These are backend-dependent and compiled according to specs given by the backend.

```stick
let msg = .to_js "Hello world"
extern "console.log(msg)"
```

The inline code can only be written inside string literal, you can use multiline string for complex codes. Additionally, you can specify its language.

```stick
let greeter = extern[ts]
"""
(name: string) => {
    console.log(`hello ${name}`)
}
"""
```
