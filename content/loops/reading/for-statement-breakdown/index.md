---
title: "Breaking Down the for Statement"
date: 2023-08-28T09:21:11-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Having seen several examples, we will now explore the syntax of a `for` loop
in more depth.

Recall the first example of a `for` loop that we looked at.

```js {linenos=table}
for (let i = 0; i < 51; i++) {
   console.log(i);
}
```

We broke down the flow of execution of this loop, noting that the loop executes
once for each of the values of `i` from 0...50. The three components of the
loop---loop variable, loop condition, and update expression---dictate exactly
how this loop executes. So far, we have only seen `for` loops with this exact
form:

```js {linenos=table}
for (let i = 0; i < upperBound; i++) {
   // loop body
}
```

However, the three components of a `for` loop statement can take different
forms to create more complex looping behavior.

## `for` Loop Anatomy

The general form of a `for` loop is:

```console
for (initial expression; loop condition; update expression) {
   loop body
}
```

Let's look at each of the three components that affect how this loop iterates.

### Initial Expression

The **initial expression** is executed once, before any iterations of the loop.
It can be any expression, even the **empty expression** (which contains no
code). However, it almost always declares and initializes a variable, known as
the **loop variable**.

The loop variable can be initialized to any value.

{{% notice blue "Example" "rocket" %}}

   This loop prints 3...9.

   ```js {linenos=table}
   for (let i = 3; i < 10; i++) {
      console.log(i);
   }
   ```

   This loop prints each of the letters `C`, `o`, `d`, and `e` on a separate line.

   ```js {linenos=table}
   let name = "LaunchCode";

   for (let i = 6; i < name.length; i++) {
      console.log(name[i]);
   }
   ```

{{% /notice %}}

To avoid confusion and bugs, you should give your loop variable a unique name, one that you have not used elsewhere in your program. In cases where the loop variable is serving as a "counter" for iterations of a loop, it is conventional to use `i` for the variable name. In the case of nested `for` loops (loops inside of loops), the variables `j`, `k`, etc. are often used.

{{% notice blue "Note" "rocket" %}}
   The loop variable is typically used by the loop body, but this is not
   required. The following example is a valid `for` loop that prints
   `"LaunchCode"` 42 times.

   ```js {linenos=table}
   for (let i = 0; i < 42; i++) {
      console.log("LaunchCode");
   }
   ```
{{% /notice %}}

### Loop Condition

The **loop condition** is executed before each loop iteration. It is *always* a
boolean expression, evaluating to `true` or `false`. If the condition is
true, the loop body executes. If the condition is false, loop execution stops
and the program continues with the next line of code below the loop.

{{% notice blue "Example" "rocket" %}}
   This loop does not iterate at all, because its condition is false to start with.

   ```js {linenos=table}
   for (let i = 0; i < -1; i++) {
      console.log("LaunchCode");
   }
   ```

{{% /notice %}}

It is critical that the loop condition *eventually* becomes false. A loop for
which the condition is never false is known as an **infinite loop**, because it
never stops iterating. A program that contains an infinite loop will only stop
after running out of memory or being manually stopped (for example, using
control+c in a terminal).

{{% notice blue "Example" "rocket" %}}

   This is an infinite loop, because its condition will always be true.

   ```js {linenos=table}
   for (let i = 0; i > -1; i++) {
      console.log("LaunchCode");
   }
   ```

{{% /notice %}}

You will accidentally write an infinite loop at some point; doing so is a rite
of passage for new programmers. When this happens, don't panic. Stop your
program and figure out why your loop condition never became false.

### Update Expression

The final component in a for loop definition is the **update expression**,
which executes after *every* iteration of the loop. While this expression may
be anything, it most often updates the value of the loop variable.

In all of the examples we have seen so far, the update expression has been
`i++`, incrementing the loop variable by 1. However, it can update the loop
variable in other ways.

{{% notice blue "Example" "rocket" %}}
   This loop prints *even* integers from 0...50.

   ```js {linenos=table}
   for (let i = 0; i < 51; i = i + 2) {
      console.log(i);
   }
   ```
{{% /notice %}}

A bad choice of update expression can also cause an *infinite loop*.

{{% notice blue "Example" "rocket" %}}
   This loop repeats indefinitely, since `i` becomes smaller with each
   iteration and thus is never greater than or equal to 51.

   ```js {linenos=table}
   for (let i = 0; i < 51; i--) {
      console.log(i);
   }
   ```
{{% /notice %}}

{{% notice blue "Example" "rocket" %}}

   How does each of the three components affect the behavior of a `for` loop? Open `Loop-Variable.js` in `loops/chapter-examples` in `javascript-projects`.
   In this file, experiment by modifying each of them in this example: the variable
   initialization, the boolean condition, and the update expression.

   ```js {linenos=table}
   for (let i = 0; i < 51; i++) {
      console.log(i);
   }
   ```

{{% /notice %}}

## Check Your Understanding

Consider the program:

```js {linenos=true}
let phrase = "Chili Cook-off";

for (let i = 0; i < phrase.length - 1; i = i + 3) {
   console.log(phrase[i]);
}
```

{{% notice green "Question" "rocket" %}}

   How many times does the loop body execute?

   1. 5
   1. 6
   1. 17
   1. 18

{{% /notice %}}

<!-- 5 times! -->

{{% notice green "Question" "rocket" %}}

   Which set of characters is printed by the loop? (We have placed characters for the choices below on the same line, but they would be on separate lines in the actual program output.)

   1. `'Chili Cook-off'`
   1. `'Chili Cook'`
   1. `'ClCk-f'`
   1. `'ClCkf'`

{{% /notice %}}

<!-- d, ClCkf>