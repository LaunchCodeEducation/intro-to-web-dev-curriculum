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

Errors are a part of coding. Occasionally, we make mistakes as programmers.
However, we are always trying to fix those mistakes by reading different
resources, examining a list of error messages (also called the **stacktrace**),
or asking for help.

Earlier in this course, we learned about two different types of errors: runtime
and logic. A logic error is when your program executes without breaking, but
doesn't behave the way you thought it would. These logic errors usually require
you to consider how you are going about solving the issue to resolve. Runtime
errors are when your program does not run correctly, and an exception is
raised.

An **exception** is a runtime error in which a name and message are displayed
to provide more information about the error.

## Exceptions and Errors

In JavaScript a runtime error and an exception are the same thing and can be
used interchangeably. This can cause confusion because a logic error is not an
exception!

## Error Object

When a runtime error, also known as an exception, is raised JavaScript returns
an `Error` object. An Error Object has two properties: a name and a message.
The name refers to the type of error that occurred, while the message gives the
user information on why that exception occurred.

JavaScript has built-in exceptions with pre-defined names and messages,
however, JavaScript also gives you the ability to create your own error
messages.

You have undoubtedly experienced various Exceptions already throughout this
class. Let's look at a few common Exceptions.

## Common Exceptions

JavaScript has some built-in Exceptions you may have already encountered in
this class.

One of the most common errors in JavaScript is a `SyntaxError` which is
thrown when we include a symbol JavaScript is not expecting.

{{% notice blue Example "rocket" %}}
```javascript
console.log("This is" an example);
```

**Console Output**

```console
SyntaxError: missing ) after argument list
```

We put our second quotation mark in the incorrect place. JavaScript does not know what to do with the second half of our phrase and throws a `SyntaxError` with the message: `missing ) after argument list`.
{{% /notice %}}


A `ReferenceError` is thrown when we try to use a variable that has not yet
been defined.

{{% notice blue Example "rocket" %}}
```javascript
console.log(x[0]);
```

**Console Output**

```console

ReferenceError: x is not defined
```

We attempt to print out the first element in the variable x, but we never declared x. JavaScript throws a `ReferenceError` with the message: `x is not defined`.

{{% /notice %}}

A `TypeError` is thrown when JavaScript expects something to be one type, but
the provided value is a different type.

{{% notice blue Example "rocket" %}}
```javascript
const a = "Launch";

a = "Code";
```

**Console Output**

```console
TypeError: invalid assignment to const 'a'
```
{{% /notice %}}

In this case, we declare a constant as the string "Launch", and then try to
change the immutable variable to "Code". JavaScript throws a `TypeError` with
the message: `invalid assignment to const 'a'`.

Exceptions give us a way to provide more information on how something went
wrong. JavaScript's built-in Exceptions are regularly used in the debugging
process.

There are more built-in Exceptions in JavaScript, you can read more by
referencing the [MDN Errors Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors) or
[W3Schools JavaScript Error](https://www.w3schools.com/js/js_errors.asp)
(scroll down to the Error Object section).

In the next section we will learn how to raise our own exceptions using the
`throw` statement.

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is the difference between a runtime error, and a logic error?

<!-- Solution: Runtime errors are when your program does not run correctly, and an exception is raised, A logic error is when your program executes without breaking, but doesn't behave the way you thought it would -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
What are some of the common errors included in JavaScript?

<!-- Solution: SyntaxError, ReferenceError, TypeError -->
{{% /notice %}}