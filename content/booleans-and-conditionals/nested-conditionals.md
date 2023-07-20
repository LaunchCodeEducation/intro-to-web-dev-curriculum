# Nested Conditionals

We can write code with more complex branching behavior by combining
conditionals and, in particular, by nesting conditionals. Let\'s see how
this works by tackling the following problem.

::: admonition
Example

Write code that prints different messages based on the value of a number
variable. If the number is odd, print nothing. If it is even, print
\"EVEN\". If it is also positive print \"POSITIVE\".
:::

Our first attempt at a solution might look like this:

``` {.js linenos=""}
let num = 7;

if (num % 2 === 0) {
   console.log("EVEN");
}

if (num > 0) {
   console.log("POSITIVE");
}
```

**Console Output**

    POSITIVE

We find that the output is `POSITIVE`, even though 7 is odd and so
nothing should be printed. This code doesn\'t work as desired because we
only want to test for positivity when we already know that the number is
even. We can enable this behavior by putting the second conditional
*inside* the first.

::: {.replit linenos="" slug="Positive-and-Even"}
js

let num = 7;

if (num % 2 === 0) {

:   console.log(\"EVEN\");

    if (num \> 0) {

    :   console.log(\"POSITIVE\");

    }

}
:::

::: admonition
Try It!

Run the previous example with several different values for `num` (even,
odd, positive, negative) to ensure it works as desired. Nice, huh?
:::

Notice that when we put one conditional inside another, the body of the
nested conditional is indented by two tabs rather than one. This
convention provides an easy, visual way to determine which code is part
of which conditional.

## Check Your Understanding

::: admonition
Question

What is printed when the following code runs?

``` {.js linenos=""}
let num = 7;

if (num % 2 === 0) {
    if (num % 2 === 1) {
        console.log("odd");
    }
}
```

1.  The code won\'t run due to invalid syntax
2.  `odd`
3.  `even`
4.  The code runs but doesn\'t print anything
:::

::: admonition
Question

Considering the same conditional used in the previous question, which
values of `num` would result in `"odd"` being printed?

``` {.js linenos=""}
if (num % 2 === 0) {
    if (num % 2 === 1) {
        console.log("odd");
    }
}
```

1.  Even values of `num`.
2.  Odd values of `num`.
3.  No values. It is impossible for the call to `console.log` to ever
    run, given the two conditions.
4.  `num` is 0.
:::
