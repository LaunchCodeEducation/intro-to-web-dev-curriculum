---
title: "Functions as Objects"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Functions are powerful tools in any programming language, and JavaScript uses these tools in some flexible and creative ways. This chapter introduces a bit more of the power of functions.

## Functions Are Objects

We [defined a value]({{< relref "../../../data-and-variables/reading/values-and-data-types/_index.md" >}}) as "a specific piece of data." Some examples are the number `42`, the string `"LC101"`, and the array `["MO", "FL", "DC"]`. *Functions appear to be very different from other keywords we have worked with, they share many core characteristics.

In particular, functions have a data type, similar to other javascript objects. Recall that a **data type** is a group of values that share characteristics, such as strings and numbers. Strings share the characteristics of having a length, while numbers don't. Numbers can be manipulated in ways that strings cannot, via operations like division and subtraction. 

{{% notice blue Example "rocket" %}}
The data type of the type conversion function `Number` is `function`. In fact, all functions are of type `function`.

```javascript
console.log(typeof 42);
console.log(typeof "LC101");
console.log(typeof Number);  
```

**Console Output**

```console
number
string
function
```
{{% /notice %}}

Like other data types, functions may be assigned to variables. If we create a function named `hello`, we can assign it to a variable with this syntax:

```javascript
function hello() {

    // function body
}

let helloFunc = hello;
```

When a variable refers to a function, we can use the variable name to *call* the function:

```javascript
helloFunc();
```

The variable `helloFunc` can be thought of as an *alias* for the function `hello`. When we call the function `helloFunc`, JavaScript sees that it refers to the function `hello` and calls that *specific* function. 

When we use a variable *name*, we are really using its *value*. If the variable `course` is assigned the value `"LC101"`, then `console.log(course)` prints `"LC101"`. When a variable holds a function, it behaves the same way as when it holds a number or a string. The variable *refers to* the function. 

<!-- ![The variable helloFunc on the left *referst to* the function hello on the right](pictures/function-var.png?classes=border) -->

Again, functions can be used in different ways. For example:

- Functions may be assigned to variables.
- Functions may be used in expressions, such as comparisons.
- Functions may be printed using `console.log`.
- Functions may be passed as arguments to other functions.
- Functions may be returned from other functions. 

Some of these function behaviors do not prove to be useful. However, other behaviors, like passing functions as arguments and assigning them to variables, turn out to be *extremely* useful.
