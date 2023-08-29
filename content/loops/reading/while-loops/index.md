---
title: "while Loops"
date: 2023-08-28T09:21:11-05:00
draft: false
weight: 6
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

There is another JavaScript construct that can also be used for iteration, the
`while` loop. The `while` loop provides a much more general mechanism for
iterating. Like a `for` loop, it uses a condition to determine whether the
loop body will continue to execute. Unlike a `for` loop, however, it does not
have initial and update expressions.

## `while` Loop Syntax

The general syntax of a `while` loop looks like this:

```console
   while (boolean expression) {
      body
   }
```

A `while` loop will continue to repeat as long as its boolean expression
evaluates to `true`. The condition typically includes a value or variable
that is updated within the loop, so that the expression eventually becomes
false.

## Flow of Execution of the `while` Loop

We can visualize the flow of execution of a `while` loop as follows.

Here is the flow of execution for a `while` loop:

1. Evaluate the condition, which yields a value of `true` or `false`.
1. If the condition is `false`, exit the `while` loop and continue
   execution at the next statement after the loop body.
1. If the condition is `true`, execute the loop body and then go back to step
   1.

## `for` Loops Rewritten as `while` Loops

We can use the `while` loop to create any type of iteration we wish,
including anything that we have previously done with a `for` loop. For
example, consider our initial `for` loop example.

```js {linenos=table}
for (let i = 0; i < 51; i++) {
   console.log(i);
}
```

This can be rewritten as a while loop. Check out `while-Loop-Example.js` in `loops/chapter-examples` in `javascript-projects` to see how!

```js {linenos=true}
let i = 0;

while (i < 51) {
   console.log(i);
   i++;
}
```

Instead of relying on the initial and update expressions, as we do in a
`for` loop, we must manage the state of our loop manually. To do this,
*before* entering the `while` loop, we will create the variable `i` and
initialize it to 0, the first number we want to print. This variable plays the
same role as the loop variable in a `for` loop. Every iteration will print
`i` and then increment `i` to the next value, until it reaches the value
51. The loop continues to iterate until the condition `i < 51` evaluates to
`false`.

You can almost read the `while` statement as if it were in a natural
language: *while `i` is less than `51`, continue executing the body of the
loop*.

{{% notice blue "Example" %}}
   What happens if you forget to include `i++` at the end of the `while` loop above?
{{% /notice %}}

## Beyond `for` Loops

We stated earlier that `while` loops are more flexible than `for` loops.
Now we will look at an example that illustrates this.

This program is an example of **input validation**. It prompts the user to
enter a positive number, converting the input string to the number data type.
If the number is not positive, then the user is prompted again within the body
of the loop. As long as the user continues to input non-positive numbers, the
loop will continue to iterate.

```js {linenos=true}
   const input = require('readline-sync');

   let num = input.question('Please enter a positive number:');
   num = Number(num);

   while (num <= 0) {
      num = input.question('Invalid input. Please enter a positive number:');
      num = Number(num);
   }
```

This example illustrates the additional flexibility provided by `while`
loops. While we use `for` loops to iterate over fixed collections (a string,
an array, a collection of integers), the `while` loop can be used to iterate
in more general circumstances. For the input validation example, at runtime it
cannot be determined how many times the loop will repeat.

## Infinite Loops, Revisited

It is easier to create an infinite `while` loop than an infinite `for`
loop. To see this, consider what happens to our first `while` loop example
if we forget to update the loop variable.

```js {linenos=table}
let i = 0;

while (i < 51) {
   console.log(i);
}
```

This is an infinite loop. The variable `i` is initialized to 0 and never
updated, so the condition `i < 51` will always be true. If you ran this
program, you would see an never-ending list of zeros.

Even when we remember to update the counter, we must be careful to make sure
that the condition will eventually be `false`.

```js {linenos=table}
let i = 0;

while (i < 51) {
   console.log(i);
   i--;
}
```

In this case, `i--` decreases the value of the counter. Since `i` starts at
0, `i < 51` will always be true. If you ran this program, you would see an
ever-expanding list of negative numbers.

{{% notice green "Tip" "rocket" %}}
   At some point, everyone creates an infinite loop. When this happens to you,
   typing `control-c` will usually force your program to stop.
{{% /notice %}}

## Check Your Understanding

{{% notice green "Question" "rocket" %}}

   True/False: You can rewrite any `for` loop as a `while` loop.

{{% /notice %}}

{{% notice green "Question" "rocket" %}}

   The following code contains an infinite loop. Which is the best explanation for why the loop does not terminate?

   ```js {linenos=table}
   let n = 10;
   let answer = 1;

   while (n > 0) {
      answer = answer + n;
      n = n + 1;
   }

   console.log(answer);
   ```

   1. `n` starts at 10 and is incremented by 1 each time through the loop, so it will always be positive.
   1. `answer` starts at 1 and is incremented by `n` each time, so it will always be positive
   1. You cannot compare `n` to 0 in a `while` loop. You must compare it to another variable.
   1. In the `while` loop body, we must set `n` to `false`, and this code does not do that.

{{% /notice %}}