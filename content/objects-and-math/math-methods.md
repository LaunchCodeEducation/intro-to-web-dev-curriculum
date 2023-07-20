# Math Methods

As with strings and arrays, JavaScript provides some built-in *methods*
for the `Math` object. These allow us to perform calculations or tasks
that are more involved than simple multiplication, division, addition,
or subtraction.

## Common Math Methods

The `Math` object contains over 30 methods. The table below provides a
sample of the most frequently used options. More complete lists can be
found here:

1.  [W3 Schools Math
    Reference](https://www.w3schools.com/jsref/jsref_obj_math.asp)
2.  [MDN Web
    Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

To see detailed examples for a particular method, click on its name.

  Method                                                           Syntax                  Description
  ---------------------------------------------------------------- ----------------------- ------------------------------------------------------------------
  `abs <abs-examples>`{.interpreted-text role="ref"}               `Math.abs(number)`      Returns the positive value of `number`.
  `ceil <ceilfloortrunc-examples>`{.interpreted-text role="ref"}   `Math.ceil(number)`     Rounds the decimal `number` UP to the closest integer value.
  `floor <floor>`{.interpreted-text role="ref"}                    `Math.floor(number)`    Rounds the decimal `number` DOWN to the closest integer value.
  `max <max-and-min-examples>`{.interpreted-text role="ref"}       `Math.max(x,y,z,...)`   Returns the largest value from a set of numbers.
  `min <min>`{.interpreted-text role="ref"}                        `Math.min(x,y,z,...)`   Returns the smallest value from a set of numbers.
  `pow <pow-examples>`{.interpreted-text role="ref"}               `Math.pow(x,y)`         Returns the value of x raised to the power of y (x ^y^).
  `random <random-examples>`{.interpreted-text role="ref"}         `Math.random()`         Returns a random decimal value between 0 and 1, NOT including 1.
  `round <round-examples>`{.interpreted-text role="ref"}           `Math.round(number)`    Returns `number` rounded to the nearest integer value.
  `sqrt <square-root>`{.interpreted-text role="ref"}               `Math.sqrt(number)`     Returns the square root of `number`.
  `trunc <trunc>`{.interpreted-text role="ref"}                    `Math.trunc(number)`    Removes any decimals and returns the integer part of `number`.

  : Ten Common Math Methods

## Check Your Understanding

Follow the links in the table above for the `floor`, `random`, `round`,
and `trunc` methods. Review the content and then answer the following
questions.

::: admonition
Question

Which of the following returns `-3` when applied to `-3.87`?

a.  `Math.floor(-3.87)`
b.  `Math.random(-3.87)`
c.  `Math.round(-3.87)`
d.  `Math.trunc(-3.87)`
:::

::: admonition
Question

What is printed by the following program?

``` {.js linenos=""}
let num = Math.floor(Math.random()*10);

console.log(num);
```

a.  A random number between 0 and 9.
b.  A random number between 0 and 10.
c.  A random number between 1 and 9.
d.  A random number between 1 and 10.
:::

::: admonition
Question

What is printed by the following program?

``` {.js linenos=""}
let num = Math.round(Math.random()*10);

console.log(num);
```

a.  A random number between 0 and 9.
b.  A random number between 0 and 10.
c.  A random number between 1 and 9.
d.  A random number between 1 and 10.
:::
