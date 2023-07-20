# Exceptions as Control Flow

Runtime errors occur as the program runs, and they are also called
exceptions. Exceptions are caused by referencing undeclared variables
and invalid or unexpected data.

## Control Flow

::: index
! control flow
:::

The **control flow** of a program is the order in which the statements
are executed. Normal control flow runs from top to bottom of a file. An
exception breaks the normal flow and stops the program. A stopped
program can no longer interact with the user. Luckily JavaScript
provides a way to anticipate and handle exceptions.

## Catching an Exception

::: index
! try catch
:::

JavaScript provides `try` and `catch` statements that allow us to keep
our programs running even if there is an exception. We can tell
JavaScript to *try* to run a block of code, and if an exception is
thrown, to *catch* the exception and run a specific block of code.
Anticipating and catching the exception makes the exception now part of
the control flow.

::: admonition
Note

Catching an exception is also known as *handling* an exception.
:::

::: admonition
Example

In this example there is an array of animals. The user is asked to enter
the index for the animal they want to see. If the user enters an index
that does NOT contain an animal, the code will throw a `TypeError` when
`name` is referenced on an undefined value.

There is a `try` block around the code that will throw the `TypeError`.
There is a `catch` block that catches the error and contains code to
inform the user that they entered an invalid index.

::: {.replit slug="control-flow-type-error" linenos=""}
js

const input = require(\'readline-sync\');

let animals = \[{name: \'cat\'}, {name: \'dog\'}\]; let index =
Number(input.question(\"Enter index of animal:\"));

try {

:   console.log(\'animal at index:\', animals\[index\].name);

} catch(err) {

:   console.log(\"We caught a TypeError, but our program continues to
    run!\"); console.log(\"You tried to access an animal at index:\",
    index);

}

console.log(\"the code goes on\...\");
:::

**Console Output**

If the user enters `9`: :

    Enter index of animal: 9
    We caught a TypeError, but our program continues to run!
    You tried to access an animal at index: 9
    the code goes on...

If the user enters `0`: :

    Enter index of animal: 0
    animal at index: cat
    the code goes on...
:::

On line 8 of the above code sample, a variable called `err` is passed to
`catch`. `err` can be any type of error object in JavaScript. For the
above example, that is a `TypeError`, but we could have had a
`ReferenceError` or `EvalError`. If necessary, we could output different
statements based on what kind of error `err` is.

::: admonition
Tip

`catch` blocks only execute if an exception is thrown
:::

## Finally

::: index
! finally
:::

::: index
single: try catch; finally
:::

JavaScript also provides a `finally` block which can be used with `try`
and `catch` blocks. A `finally` block code runs after the `try` and
`catch`. What is special about `finally` is that `finally` code block
ALWAYS runs, even if an exception is NOT thrown.

::: admonition
Example

Let\'s update the above example to print out the index the user entered.
We want this message to be printed EVERY time the code runs. Notice the
`console.log` statement on line 11.

::: {.replit slug="control-flow-type-error-finally" linenos=""}
js

const input = require(\'readline-sync\');

let animals = \[{name: \'cat\'}, {name: \'dog\'}\]; let index =
Number(input.question(\"Enter index of animal:\"));

try {

:   console.log(\'animal at index:\', animals\[index\].name);

} catch(err) {

:   console.log(\"We caught a TypeError, but our program continues to
    run!\");

} finally {

:   console.log(\"You tried to access an animal at index:\", index);

}

console.log(\"the code goes on\...\");
:::

**Console Output**

If the user enters `7`: :

    Enter index of animal: 7
    We caught a TypeError, but our program continues to run!
    You tried to access an animal at index: 7
    the code goes on...

If the user enters `1`: :

    Enter index of animal: 1
    animal at index: dog
    You tried to access an animal at index: 1
    the code goes on...
:::

## Check Your Understanding

::: admonition
Question

What statement do we use if we want to attempt to run code, but think an
exception might be thrown?

1.  `catch`
2.  `try`
3.  `throw`
4.  `finally`
:::

::: admonition
Question

How do you handle an exception that is thrown?

1.  With code placed within the `try` block.
2.  With code placed within the `catch` block.
3.  With code placed within a `throw` statement.
4.  With code placed within the `finally` block.
:::

::: admonition
Question

What statement do you use to ensure a code block is executed regardless
if an exception was thrown?

1.  `throw`
2.  `catch`
3.  `try`
4.  `finally`
:::
