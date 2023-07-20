# Using Functions

Having informally used and discussed functions, it is time to formalize
a few concepts.

::: index
single: function; call single: function; argument single: function;
invocation single: function; input
:::

A **function call** is the act of using a function by referring to its
name, followed by parentheses. A synonymous term is **function
invocation**, and we will sometimes say that we are \"invoking a
function.\"

Within parentheses, a comma-separated list of **arguments** may be
provided when calling a function. These are sometimes called **inputs**,
and we say that the inputs are \"passed to\" the function.

A generic function call looks like this:

    functionName(argument1, argument2,...,argumentN);

::: index
single: value; return single: function; return value
:::

Every function provides a **return value**, which can be used by the
calling program\-\--for example, to store in a variable or print to the
console.

::: admonition
Example

A return value may be stored in a variable.

``` js
let stringVal = String(42);
```

It may also be used in other ways. For example, here we use the return
value as the input argument to `console.log` without storing it.

``` js
console.log(String(42));
```

**Console Output**

    42
:::

If a function doesn\'t provide an explicit return value, the special
value `undefined` will be returned.

::: admonition
Example

``` {.js linenos=""}
let returnVal = console.log("LaunchCode");
console.log(returnVal);
```

**Console Output**

    LaunchCode
    undefined
:::

::: warning
::: title
Warning
:::

The special value `undefined` is built into JavaScript. As with
booleans, it is not a string, so `undefined === "undefined"` returns
`false`.
:::

::: index
single: function; side effect
:::

In some cases, calling a function results in an action that changes the
state of a program outside of the function itself. Such a behavior is
known as a **side effect**.

::: admonition
Example

Calling `console.log` results in output to the console, which is a side
effect.
:::
