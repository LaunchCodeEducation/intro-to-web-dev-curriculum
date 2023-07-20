# Primitive Data Types

::: index
! primitive
:::

In JavaScript, data types can fall into one of two categories: primitive
or object types. A **primitive** data type is a basic building block.
Using primitive data types, we can build more complex data structures or
object data types.

While object types such as objects and arrays are mutable, primitive
data types are immutable. Immutable data types are data types that
cannot be changed once the value has been created.

Primitive data types include:

1.  Strings
2.  Numbers
3.  Booleans
4.  `undefined`
5.  `null`

## `undefined`

`undefined` is a primitive data type in JavaScript which is assigned to
declared variables, which have *not* been initialized.

``` {.js linenos=""}
let x;
console.log(x)
```

Console Output

``` bash
undefined
```

## `null`

`null` is similar to `undefined` in that it represents an unknown value,
however, it is assigned to values that the programmer wishes to keep
empty.

``` js
let x = null;
console.log(x);
```

Console Output

``` bash
null
```

## Example

Let\'s say that we are still working for the zoo. We have objects
created for animals like so:

``` {.js linenos=""}
let giraffe = {
   species: "Reticulated Giraffe",
   name: "Cynthia",
   weight: 1500,
   age: 15,
   diet: "leaves"
};
```

Now, a new giraffe is coming to the zoo. We may want to initialize an
object for the giraffe, but hold off on storing information in the
`weight` property until the giraffe arrives. In this case, we could
initialize the `weight` property like so:

``` {.js linenos=""}
let giraffeTwo = {
   species: "Reticulated Giraffe",
   name: "Alicia",
   weight: null,
   age: 10,
   diet: "leaves"
};
```

This way, our object is properly initialized with all of the information
we would need and we can update the `weight` property later when we have
accurate information.

## Check Your Understanding

::: admonition
Question

Which of the following are primitive data types? Mark ALL that apply.

a.  arrays
b.  Strings
c.  objects
d.  `null`
:::

::: admonition
Question

Consider the following code block:

``` {.js linenos=""}
let x;

console.log(x);
```

`x` is of what data type?

a.  `null`
b.  `undefined`
c.  `NaN`
d.  number
:::
