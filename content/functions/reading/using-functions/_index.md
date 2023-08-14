---
title: "Using Functions"
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

Having informally used and discussed functions, it is time to formalize a few concepts.

A **function call** is the act of using a function by referring to its name, followed by parentheses. A synonymous term is **function invocation**, and we will sometimes say that we are "invoking a function."

Within parentheses, a comma-separated list of **arguments** may be provided when calling a function. These are sometimes called **inputs**, and we say that the inputs are "passed to" the function.

A generic function call looks like this:

```console
functionName(argument1, argument2,...,argumentN);
```

Every function provides a **return value**, which can be used by the calling program---for example, to store in a variable or print to the console.

{{% notice blue Example "rocket" %}}
A return value may be stored in a variable.

```javascript
let stringVal = String(42);
```
   
It may also be used in other ways. For example, here we use the return value as the input argument to `console.log` without storing it.

```javascript
console.log(String(42));

```
   
**Console Output**

```console
42
```
{{% /notice %}}

If a function doesn't provide an explicit return value, the special value `undefined` will be returned.

{{% notice blue Example "rocket" %}}
```javascript
let returnVal = console.log("LaunchCode");
console.log(returnVal);
```

**Console Output**

```console
LaunchCode
undefined
```
{{% /notice %}}

{{% notice orange Warning "rocket" %}}
The special value `undefined` is built into JavaScript. As with booleans, it is not a string, so `undefined === "undefined"` returns `false`.
{{% /notice %}}

In some cases, calling a function results in an action that changes the state of a program outside of the function itself. Such a behavior is known as a **side effect**. 

{{% notice blue Example "rocket" %}}
Calling `console.log` results in output to the console, which is a side effect. 
{{% /notice %}}