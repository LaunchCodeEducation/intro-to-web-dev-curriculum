---
title: "Introduction"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In the [functions chapter]({{< relref "../../../functions/reading/parameter-variables/_index.md#function-scope" >}}), we saw that *where* variables
are declared and initialized in the code affects when they can be used. This
idea is called **scope**, and it describes the ability of a program to access
or modify a variable.

{{% notice blue Example "rocket" %}}
```javascript
let a = 0;

function coolFunction() {
    let b = 2;
    return a + b;
}
```

`a` is accessible *inside* and *outside* of `coolFunction()`.

`b` is only accessible *inside* of `coolFunction()`.
{{% /notice %}}

Let's add some `console.log` statements to explore this code snippet.

{{% notice blue Example "rocket" %}}
```javascript
let a = 0;
console.log(a);

function coolFunction() {
    let b = 2;
    console.log(`a = ${a}, b = ${b}.`);
    return a + b;
}

a += 1;
console.log(a);

coolFunction();
console.log(b);
```

**Console Output**

```console
0
1
a = 1, b = 2.
ReferenceError: b is not defined
```
{{% /notice %}}

1. Lines 2 and 11 print the initial and incremented values of `a`.
1. Line 13 calls `coolFunction()`, and line 6 prints the values of `a` and `b`. This shows that both variables are accessible within the function.
1. Line 14 throws a ReferenceError, showing that `b` is not accessible outside of `coolFunction`.

## Block/Local Scope

**Local scope** refers to variables declared and initialized inside a function
or block. A *locally scoped* variable can only be referenced inside of the
block or function where it is defined. In the example above, `b` has a local
scope limited to `coolFunction()`. Referencing or attempting to update  `b`
outside of the function leads to a scoping error.

{{% notice blue "Try it!" "rocket" %}}
The following code block has an error related to scope. Try to fix it!

```javascript
function myFunction() {
    let i = 10;
    return 10 + i;
}

console.log(i);
```
{{% /notice %}}

## Global Scope

**Global scope** refers to variables declared and initialized outside of a
function and in the main body of the file. These variables are accessible to
any function within a file. In the first example above, `a` has global scope.

Global scope is the default in JavaScript. If you assign a value to a variable
WITHOUT first declaring it with `let` or `const`, then the variable
automatically becomes global.

{{% notice blue Example "rocket" %}}

{{% /notice %}}

```javascript
// Code here CAN use newVariable.

function coolFunction() {
    newVariable = 5;
    return newVariable;
}

// Code here CAN use newVariable.
```

{{% notice orange Warning "rocket" %}}
In the loop `for (i = 0; i < string.length; i++)`, leaving off the `let` from `i = 0` means that `i` is treated as a global variable. ANY other portion of the program can access or modify `i`, which could
disrupt how well the loop operates.
{{% /notice %}}

## Execution Context

**Execution context** refers to the conditions under which a variable is
executed---its scope. Scoping affects the variable's behavior at runtime.
When the code is run in the browser, everything is first run at a global
context. As the compiler processes the code and finds a function, it shifts
into the function context before returning to global execution context.

Let's consider this code:

```javascript
let a = 0;

function coolFunction() {
    let b = 2;
    return a + b;
}

function coolerFunction() {
    let c = 5;
    c += coolFunction();
    return c;
}

console.log(coolFunction());
console.log(coolerFunction());
```

Now, let's consider the execution context for each step.

1. First, the global execution context is entered as the compiler executes the code.


![Figure showing global execution context at the bottom of the stack.](pictures/globalexecutioncontext.png?classes=border)

1. Once `coolFunction()` is hit, the compiler creates and executes `coolFunction()` under the `coolFunction()` execution context.

![Figure showing coolFunction on top of global execution context.](pictures/coolFunction.png?classes=border)

1. Upon completion, the compiler returns to the global execution context.

![Figure showing global execution context at the bottom of the stack.](pictures/globalexecutioncontext.png?classes=border)

1. The compiler stays at the global execution context until the creation and execution of `coolerFunction()`.

![Figure showing coolerFunction on top of the global execution context.](pictures/coolerFunction.png?classes=border)

1. Inside of `coolerFunction()` is a call to `coolFunction()`. The compiler will go up in execution context to `coolFunction()` before returning down to `coolerFunction()`'s execution context. Upon completion of that function, the compiler returns to the global execution context.

![Figure showing coolFunction on top of coolerFunction on top of the global execution context.](pictures/coolandcoolerFunction.png?classes=border)

![Figure showing coolerFunction on top of the global execution context.](pictures/coolerFunction.png?classes=border)

![Figure showing global execution context at the bottom of the stack.](pictures/globalexecutioncontext.png?classes=border)

## Check Your Understanding

Both of the concept checks refer to the following code block:

```javascript
function myFunction(n) {
    let a = 100;
    return a + n;
}

let x = 0;

x = myFunction(x);
```

{{% notice green Question "rocket" %}}
What scope is variable `x`?

1. Global
1. Local
{{% /notice %}}

{{% notice green Question "rocket" %}}
In what order will the compiler execute the code?
{{% /notice %}}