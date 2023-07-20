# Introduction

::: index
! scope
:::

In the `Functions chapter <function-scope>`{.interpreted-text
role="ref"}, we saw that *where* variables are declared and initialized
in the code affects when they can be used. This idea is called
**scope**, and it describes the ability of a program to access or modify
a variable.

::: admonition
Example

``` {.js linenos=""}
let a = 0;

function coolFunction() {
   let b = 2;
   return a + b;
}
```

`a` is accessible *inside* and *outside* of `coolFunction()`.

`b` is only accessible *inside* of `coolFunction()`.
:::

Let\'s add some `console.log` statements to explore this code snippet.

::: admonition
Example

``` {.JavaScript linenos=""}
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

    0
    1
    a = 1, b = 2.
    ReferenceError: b is not defined
:::

1.  Lines 2 and 11 print the initial and incremented values of `a`.
2.  Line 13 calls `coolFunction()`, and line 6 prints the values of `a`
    and `b`. This shows that both variables are accessible within the
    function.
3.  Line 14 throws a ReferenceError, showing that `b` is not accessible
    outside of `coolFunction`.

## Block/Local Scope

::: index
! local scope
:::

**Local scope** refers to variables declared and initialized inside a
function or block. A *locally scoped* variable can only be referenced
inside of the block or function where it is defined. In the example
above, `b` has a local scope limited to `coolFunction()`. Referencing or
attempting to update `b` outside of the function leads to a scoping
error.

::: admonition
Try It!

The following code block has an error related to scope. Try to fix it!

::: {.replit slug="ScopeError" linenos=""}
js

function myFunction() {

:   let i = 10; return 10 + i;

}

console.log(i);
:::
:::

## Global Scope

::: index
! global scope
:::

**Global scope** refers to variables declared and initialized outside of
a function and in the main body of the file. These variables are
accessible to any function within a file. In the first example above,
`a` has global scope.

Global scope is the default in JavaScript. If you assign a value to a
variable WITHOUT first declaring it with `let` or `const`, then the
variable automatically becomes global.

::: admonition
Example

``` {.JavaScript linenos=""}
// Code here CAN use newVariable.

function coolFunction() {
   newVariable = 5;
   return newVariable;
}

// Code here CAN use newVariable.
```
:::

::: admonition
Warning

In the loop `for (i = 0; i < string.length; i++)`, leaving off the `let`
from `i = 0` means that `i` is treated as a global variable. ANY other
portion of the program can access or modify `i`, which could disrupt how
well the loop operates.
:::

## Execution Context

::: index
! execution context
:::

**Execution context** refers to the conditions under which a variable is
executed\-\--its scope. Scoping affects the variable\'s behavior at
runtime. When the code is run in the browser, everything is first run at
a global context. As the compiler processes the code and finds a
function, it shifts into the function context before returning to global
execution context.

Let\'s consider this code:

``` {.js linenos=""}
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

Now, let\'s consider the execution context for each step.

1.  First, the global execution context is entered as the compiler
    executes the code.

    ![](figures/globalexecutioncontext.png)

2.  Once `coolFunction()` is hit, the compiler creates and executes
    `coolFunction()` under the `coolFunction()` execution context.

    ![](figures/coolFunction.png)

3.  Upon completion, the compiler returns to the global execution
    context.

    ![](figures/globalexecutioncontext.png)

4.  The compiler stays at the global execution context until the
    creation and execution of `coolerFunction()`.

    ![](figures/coolerFunction.png)

5.  Inside of `coolerFunction()` is a call to `coolFunction()`. The
    compiler will go up in execution context to `coolFunction()` before
    returning down to `coolerFunction()`\'s execution context. Upon
    completion of that function, the compiler returns to the global
    execution context.

    ![](figures/coolandcoolerFunction.png)

    ![](figures/coolerFunction.png)

    ![](figures/globalexecutioncontext.png)

## Check Your Understanding

Both of the concept checks refer to the following code block:

``` {.js linenos=""}
function myFunction(n) {
   let a = 100;
   return a + n;
}

let x = 0;

x = myFunction(x);
```

::: admonition
Question

What scope is variable `x`?

a.  Global
b.  Local
:::

::: admonition
Question

In what order will the compiler execute the code?
:::
