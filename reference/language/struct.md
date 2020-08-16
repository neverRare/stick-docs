# Struct

Structs are first class values that can hold compounded data.

```stick
let someone = (username: "someone123", email: "someone@example.com")
let another_one = :
    username: "another_one123"
    email: "another_one@example.com"
```

Oftentimes, you'll store property value in a variable with the same name as the property name before initiating structs.

```stick
let username = "someone123"
let email = "someone@example.com"
let someone = (username: username, email: email)
```

In this case, you can use a shorthand syntax.

```stick
let username = "someone123"
let email = "someone@example.com"
let someone = (username, email)
```

## Accessing values

You can access a field with `.` operator.

```stick
let email = another_one.email
```
