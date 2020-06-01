# Unpacking Assignment

Unpacking assignment is a syntactic sugar for accessing properties and assigning it to variables. This can be used for namespaces as well. Unpacking can be referred to as destructuring.

```stick
let name
let age

joe =: (name, age)

-- same as

name = joe.name
age = joe.age
```

## Renaming

It is possible to assign properties to variable with different name or other property.

```stick
let his_name
let his_age

joe =: :
    name his_name
    age his_age

-- same as

his_name = joe.name
his_age = joe.age
```

## Nesting

With renaming, it's possible to get properties of properties.

```stick
let length
let width
let height
let brand
let model

his_car =: :
    size:
        length
        width
        height

    brand
    model

-- same as

length = his_car.size.length
width = his_car.size.width
height = his_car.size.height
brand = his_car.brand
model = his_car.model
```
