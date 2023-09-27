---
title: "Recursion"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 6
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Quick Review

In the previous chapter, we learned how to define a function and its
parameters.

{{% notice blue Example "rocket" %}}
```javascript
function addTwoToNumber(num){
    return num += 2;
}

console.log(addTwoToNumber(12));
```

**Console Output**

```console
14
```
{{% /notice %}}

When called, the parameter `num` is passed an argument, which in this case is
the number `12`. The function executes and returns the value `14`, which
the `console.log` statement prints.

### Functions Can Call Other Functions

Functions should only accomplish one (preferably simple) task. To solve more
complicated tasks, one small function must call other functions.

{{% notice blue Example "rocket" %}}
```javascript
function addTwoToNumber(num){
    return num += 2;
}

function addFiveToNumber(value){
    let result = addTwoToNumber(value) + 3;
    return result;
}

console.log(addFiveToNumber(12))
```

**Console Output**

```console
17
```
{{% /notice %}}

Of course, there is no need to write a function to add 5 to a value, but the
example demonstrates calling a function from within another function.

## What Is Recursion?

In programming, the *divide and conquer* strategy solves a problem by breaking
it down into smaller, simpler pieces. If these pieces *can all be solved in
exactly the same way*, then we gain an additional advantage. Solving the big
problem becomes a process of completing and combining the smaller parts.

Splitting up a large task into smaller, identical pieces allows us to reuse a
single function rather than coding several different functions. We accomplish
this by either:

1. Setting up a loop to call one function lots of times, OR
1. Building a function that splits up the large problem for us, until a *simplest case* is found and solved.

**Recursion** is the process of solving a larger problem by breaking it into
smaller pieces that *can all be solved in exactly the same way*. The clever
idea behind recursion is that instead of using a loop, a function simply
calls *itself* over and over again, with each step reducing the size of the
problem.

Through recursion, a problem eventually gets reduced to a very simple task,
which can be immediately solved. This small answer sets up the solution for the
previous step, which in turn solves the next bigger step. Properly built, the
function combines all of the small answers to solve the original problem.

Many new programmers (and even veteran ones) find recursion an abstract and
tricky concept. One helpful way to approach the idea is to walk through an
example.
