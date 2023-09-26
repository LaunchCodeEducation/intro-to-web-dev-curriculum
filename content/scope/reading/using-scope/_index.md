---
title: "Using Scope"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Scope allows programmers to control the flow of information through the
variables in their program. Some variables you want to set as constants (like
pi), which can be accessed globally. Others you want to keep secure to minimize
the danger of accidental updates. For example, a variable holding someone's
username should be kept secure.

## Shadowing

**Variable shadowing** is where two variables in different scopes have the same
name. The variables can then be accessed under different contexts. However,
shadowing can affect the variable's accessibility. It also causes confusion for
anyone reviewing the code.

{{% notice blue Example "rocket" %}}
```javascript {linenos=true}
const input = require('readline-sync');

function hello(name) {
    console.log('Hello,', name);
    name = 'Ruth';
    return doubleName(name);
}

function doubleName(name){
    console.log(name+name);
    return name+name;
}

let name = input.question("Please enter your name: ");

hello(name);
doubleName(name);
console.log(name);
```

So, what is the value of `name` in line 4, 10, 16, 17, and 18?
{{% /notice %}}

Yikes! This is why shadowing is NOT a best practice in coding. Whenever
possible, use different global and local variable names.

{{% notice blue "Try it!" "rocket" %}}
If you are curious about the `name` values in the example, feel free to
run the code within your `javascript-projects/scope/chapter-examples` directory.
{{% /notice %}}

## Variable Hoisting

**Variable hoisting** is a behavior in JavaScript where variable declarations
are raised to the top of the current scope. This results in a program being able
to use a variable before it has been declared. Hoisting occurs when the `var`
keyword is used in the declaration, but it does NOT occur when `let` and
`const` are used in the declaration.

{{% notice blue Note "rocket" %}}
Although we don't use the `var` keyword in this book, you will see it a
lot in other JavaScript resources. Variable hoisting is an important concept
to keep in mind as you work with JavaScript.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What keyword allows a variable to be hoisted?

1. `let`
1. `var`
1. `const`

<!-- Solution: var -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Consider this code:

```javascript
let a = 0;

function myFunction() {
    let a = 10;
    return a;
}
```

Because there are two separate variables with the name, `a`, under the two different scopes, `a` is being shadowed.

a. True
b. False

<!-- Solution: true -->
{{% /notice %}}