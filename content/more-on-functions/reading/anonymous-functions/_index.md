---
title: "Anonymous Functions"
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

You already know [one method for creating a function]({{< relref "../../../functions/reading/creating-functions/_index.md#function-syntax" >}}):

```javascript
function myFunction(parameter1, parameter2,..., parameterN) {

    // function body
}
```

A function defined in this way is a **named function** (`myFunction`, in the example above).

Many programming languages, including JavaScript, allow us to create **anonymous functions**, which *do not* have names. We can create an anonymous function by simply leaving off the function name when defining it:

```javascript
function (parameter1, parameter2,..., parameterN) {

    // function body
}
```

You might be asking yourself, *How do I call a function if it doesn't have a name?!* Good question. Let's address that now.

## Anonymous Function Variables

Anonymous functions are often assigned to variables when they are created, which allows them to be called using the variable's name.

{{% notice blue Example "rocket" %}}
Let's create and use a simple anonymous function that returns the sum of two numbers.

```javascript
let add = function(a, b) {
    return a + b;
};

console.log(add(1, 1));
```

**Console Output**

```console
2
```
{{% /notice %}}

The variable `add` refers to the anonymous function created on lines 1 through 3. We call the function using the *variable* name, since the function doesn't have a name.

The visual analogy here is the same as that of a variable referring to a named function.

![The variable add on the left refers to an anonymous function on the right](pictures/function-var-anonymous.png?classes=border)

{{% notice orange Warning "rocket" %}}
Like other variable declarations, an assignment statement using an anonymous function should be terminated by a semi-colon, `;`. This is easy to overlook, since named functions do *not* end with a semi-colon.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Convert the following named function to an anonymous function that is stored in a variable.

```javascript
function reverse(str) {
    let lettersArray = str.split('');
    let reversedLettersArray = lettersArray.reverse();
    return reversedLettersArray.join('');
}
```
{{% /notice %}}

{{% notice green Question "rocket" %}}
Consider the code sample below, which declares an anonymous function
beginning on line 1.

```javascript
let f1 = function(str) {
    return str + str;
};

let f2 = f1;
```

Which of the following are valid ways of invoking the anonymous
function with the argument `"abcd"`? (Choose all that apply.)

1. `f1("abcd");`
1. `function("abcd");`
1. `f2("abcd");`
1. It is not possible to invoke the anonymous function, since it doesn’t have a name.
{{% /notice %}}

{{% notice green Question "rocket" %}}
Complete the following code snippet so that it logs an error message
if `userInput` is negative.

```javascript
let logger = function(errorMsg) {
    console.log("ERROR: " + errorMsg);
};

if (userInput < 0) {
    ____________("Invalid input");
}
```
{{% /notice %}}