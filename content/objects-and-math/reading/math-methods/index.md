---
title: "Math Methods"
date: 2023-08-31T13:16:22-05:00
draft: false
weight: 5
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

As with strings and arrays, JavaScript provides some built-in *methods* for the
`Math` object. These allow us to perform calculations or tasks that are more
involved than simple multiplication, division, addition, or subtraction.

## Common Math Methods

The `Math` object contains over 30 methods. The table below provides a sample
of the most frequently used options. More complete lists can be found here:

1. [W3 Schools Math Reference](https://www.w3schools.com/jsref/jsref_obj_math.asp)
1. [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

To see detailed examples for a particular method, click on its name.

| Method | Syntax | Description |
|--------|--------|-------------|
| [abs]({{< relref "../../../appendices/math-method-examples/abs-examples/" >}}) | `Math.abs(number)` | Returns the positive value of `number`. |
| [ceil]({{< relref "../../../appendices/math-method-examples/ceilfloortrunc-examples/" >}}) | `Math.ceil(number)` | Rounds the decimal `number` UP to the closest integer value. |
| [floor]({{< relref "../../../appendices/math-method-examples/ceilfloortrunc-examples/#mathfloor" >}}) | `Math.floor(number)` | Rounds the decimal `number` DOWN to the closest integer value. |
| [max]({{< relref "../../../appendices/math-method-examples/max-and-min-examples" >}}) | `Math.max(x,y,z,...)` | Returns the largest value from a set of numbers. |
| [min]({{< relref "../../../appendices/math-method-examples/max-and-min-examples/#mathmin" >}}) | `Math.min(x,y,z,...)` | Returns the smallest value from a set of numbers. |
| [pow]({{< relref "../../../appendices/math-method-examples/pow-examples" >}}) | `Math.pow(x,y)` | Returns the value of x raised to the power of y (x :sup:`y`). |
| [random]({{< relref "../../../appendices/math-method-examples/random-examples" >}}) | `Math.random()` | Returns a random decimal value between 0 and 1, NOT including 1. |
| [round]({{< relref "../../../appendices/math-method-examples/round-examples" >}}) | `Math.round(number)` | Returns `number` rounded to the nearest integer value. |
| [sqrt]({{< relref "../../../appendices/math-method-examples/pow-examples/#mathsqrt" >}}) | `Math.sqrt(number)` | Returns the square root of `number`. |
| [trunc]({{< relref "../../../appendices/math-method-examples/ceilfloortrunc-examples/#mathtrunc" >}}) | `Math.trunc(number)` | Removes any decimals and returns the integer part of `number`. |

## Check Your Understanding

Follow the links in the table above for the `floor`, `random`, `round`,
and `trunc` methods. Review the content and then answer the following
questions.

{{% notice green "Question" "rocket" %}}

   Which of the following returns `-3` when applied to `-3.87`?

   1. `Math.floor(-3.87)`
   1. `Math.random(-3.87)`
   1. `Math.round(-3.87)`
   1. `Math.trunc(-3.87)`

{{% /notice %}}

<!-- 1, floor -->

{{% notice green "Question" "rocket" %}}

   What is printed by the following program?

   ```js {linenos=true}
      let num = Math.floor(Math.random()*10);

      console.log(num);
   ```

   1. A random number between 0 and 9.
   1. A random number between 0 and 10.
   1. A random number between 1 and 9.
   1. A random number between 1 and 10.

{{% /notice %}}

<!-- 1, random number between 0 and 9 -->

{{% notice green "Question" "rocket" %}}

   What is printed by the following program?

   ```js {linenos=true}
      let num = Math.round(Math.random()*10);

      console.log(num);
   ```

   1. A random number between 0 and 9.
   1. A random number between 0 and 10.
   1. A random number between 1 and 9.
   1. A random number between 1 and 10.

{{% /notice %}}

<!-- 2, a random number between 0 and 10 -->