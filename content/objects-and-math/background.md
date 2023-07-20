# Objects and Why They Matter {#objects-intro}

::: index
! object, ! key/value pair, ! key
:::

So far we have learned a lot about arrays, which are data structures
that can hold many values. **Objects** are also data structures that can
hold many values.

Unlike arrays, each value in an object has a name or **key** for
reference purposes. The pairing between a key and its value is called a
**key/value pair**.

Objects store as many key/value pairs as needed, and each value needs a
key. Without a key, the value cannot be accessed or modified by the
programmer.

![](figures/object.png)

## Initializing Objects

::: index
! object literal
:::

When defining an object, we call the initialization an **object
literal**. Objects require three things for the definition: a name, a
set of keys, and their corresponding values.

::: note
::: title
Note
:::

Object literals use curly braces, `{}`, to enclose the key/value pairs.
:::

Once we have these three things, we write an object literal like so:

``` {.js linenos=""}
let objectName = {key1:value1, key2:value2, key3:value3, ... };
```

If we have a lot of key/value pairs in our object, we can also put each
one on a separate line!

``` {.js linenos=""}
let objectName = {
    key1: value1,
    key2: value2,
    key3: value3,
    .
    .
    .
};
```

::: warning
::: title
Warning
:::

When putting the key/value pairs on separate lines, it is important to
pay attention to spaces and tabs! Incorrect spacing or tab usage can
result in a bug.
:::

When defining an object, keep in mind that the keys can only be valid
JavaScript strings. The values can be any of the data types that we have
previously discussed.

::: admonition
Example

Let\'s say that we want to create a small program for a zoo. We could
create an object for storing the different data points about the animals
in a zoo. We start with our first tortoise. His name is Pete! He is an
85 year old, 919 lb Galapagos Tortoise, who prefers a diet of veggies.
Our object literal for all of this important data about Pete would be:

``` {.js linenos=""}
let tortoiseOne = {
    species: "Galapagos Tortoise",
    name: "Pete",
    weight: 919,
    age: 85,
    diet: ["pumpkins", "lettuce", "cabbage"]
};
```
:::

## Methods and Properties

::: index
! property
:::

::: index
method
:::

A **property** of an object is a key/value pair of an object. The
property\'s name is the key and the property\'s value is the data
assigned to that key.

A **method** performs an action on the object, because it is a property
that stores a function.

::: admonition
Example

In the case of Pete, our zoo\'s friendly Galapagos Tortoise, the object
`tortoiseOne` has several properties for his species, name, weight, age,
and diet. If we wanted to add a method to our object, we might add a
function that returns a helpful statement for the general public.

``` {.js linenos=""}
let tortoiseOne = {
    species: "Galapagos Tortoise",
    name: "Pete",
    weight: 919,
    age: 85,
    diet: ["pumpkins", "lettuce", "cabbage"],
    sign: function() {
        return this.name + " is a " + this.species;
    }
 };
```
:::

In the example above, on line 8, we see a keyword which is new to us.
Programmers use the `this` keyword when they call an object\'s property
from within the object itself. We could use the object\'s name instead
of `this`, but `this` is shorter and easier to read. For example, the
method, `sign`, could have a return statement of
`tortoiseOne.name + " is a " + tortoiseOne.species"`. However, that
return statement is bulky and will get more difficult to read with more
references to the `tortoiseOne` object.

## Check Your Understanding

::: admonition
Question

Which of the following is NOT a true statement about objects?

a.  Objects can store many values
b.  Objects have properties
c.  Objects have methods
d.  Keys are stored as numbers
:::

::: admonition
Question

Which keyword can be used to refer to an object within an object?

a.  `Object`
b.  `let`
c.  `this`
:::
