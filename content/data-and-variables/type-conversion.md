# Type Conversion

::: index
! Number(), ! String(), returns
:::

::: index
pair: type; conversion
:::

Sometimes it is necessary to convert values from one type to another. A
common example is when a program receives input from a user or a file.
In this situation, numeric data may be passed to the program as strings.

JavaScript provides a few simple functions that will allow us to convert
values to different data types. The functions `Number` and `String` will
(attempt to) convert their arguments into types `number` and `string`,
respectively. We call these **type conversion** functions.

The `Number` function can take a string and turn it into an integer. Let
us see this in action:

::: admonition
Example

``` {.js linenos=""}
console.log(Number("2345"));
console.log(typeof Number("2345"))
console.log(Number(17));
```

**Console Output**

    2345
    number
    17
:::

What happens if we attempt to convert a string to a number, and the
string doesn\'t directly represent a number?

::: admonition
Example

``` js
console.log(Number("23bottles"));
```

**Console Output**

    NaN
:::

This example shows that a string has to be a syntactically legal number
for conversion to go as expected. Examples of such strings are `"34"` or
`"-2.5"`. If the value cannot be cleanly converted to a number then
`NaN` will be returned, which stands for \"not a number.\"

::: index
NaN, special value
:::

::: note
::: title
Note
:::

`NaN` is a **special value** in JavaScript that represents that state of
not being a number. We will learn more about `NaN` and other special
values in a later chapter.
:::

The type conversion function `String` turns its argument into a string.
Remember that when we print a string, the quotes may be removed.
However, if we print the type, we can see that it is definitely
`'string'`.

::: admonition
Example

``` {.js linenos=""}
console.log(String(17));
console.log(String(123.45));
console.log(typeof String(123.45));
```

**Console Output**

    17
    123.45
    string
:::

## Check Your Understanding

::: admonition
Question

Which of the following strings result in `NaN` when passed to `Number`?
(Feel free to try running each of the conversions.)

1.  `'3'`
2.  `'three'`
3.  `'3 3'`
4.  `'33'`
:::
