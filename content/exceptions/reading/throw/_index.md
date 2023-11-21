---
title: "Throw"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: Colin Brock # update any time edits are made after review
lastEditorGitHub: ColinBrock # update any time edits are made after review
lastMod: 2023-11-18 # UPDATE ANY TIME CHANGES ARE MADE
---

In most programming languages, when the compiler or interpreter encounters code it doesn't know how to handle, it
**throws** an exception. This is how the compiler notifies the programmer that something has gone wrong. Throwing
an exception is also known as *raising* an exception.

JavaScript gives us the ability to raise exceptions using the `throw` statement. One reason to throw an exception
is if your code is being used in an unexpected way.

## Throw Default Error

We can throw a default Error by using the `throw` statement and passing in a string description as an argument.

{{% notice blue Example "rocket" %}}
```javascript
throw Error("You cannot divide by zero!");
```

**Console Output**

```console
Error: You cannot divide by zero!
at evalmachine.<anonymous>:1:7
at Script.runInContext (vm.js:133:20)
at Object.runInContext (vm.js:311:6)
at evaluate (/run_dir/repl.js:133:14)
```

The error text displays the error name, and it contains details about where the error was thrown.
The text `at evalmachine.<anonymous>:1:7` indicates that the error as thrown from line 1, which we know is
true because our example only has one line of code.
{{% /notice %}}

{{% notice blue Note "rocket" %}}
With all that we have learned about unit testing, you might be wondering how you test if an error is thrown when it should be.
To do so, let's imagine our example above is inside a function called `checkThrow()`. We can then use the `toThrow()` matcher like so:

```javascript
expect( function() {
    checkThrow(); 
}).toThrow(new Error('You cannot divide by zero!'));
```
{{% /notice %}}

## Pre-existing Error

JavaScript also gives us the power to throw a more specific type of error.

{{% notice blue Example "rocket" %}}
```javascript
throw SyntaxError("That is the incorrect syntax");
```

**Console Output**

```console
SyntaxError: That is the incorrect syntax
```

JavaScript gives us flexibility by allowing us to raise standard library errors and to define our own errors. We can use exceptions to allow our program to break and provide useful information as to why something went wrong.
{{% /notice %}}

## Custom Error

JavaScript will also let you define new types of Errors. You may find this helpful in the future, however, that goes beyond the scope of this class.

## Check Your Understanding

{{% notice green Question "rocket" %}}
What statement do we use to raise an exception?

<!-- Solution: throw statement -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
How do we customize the message of an exception?

<!-- Solution: by using the throw statement and passing in a string description as a argument. -->
{{% /notice %}}