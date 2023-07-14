---
title: "Other Operators"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 7
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## The String Operator `+`

So far we have only seen operators that work on operands which are of type `number`, but there are operators that work on other data types as well. In particular, the `+` operator can be used with `string` operands to **concatenate**, or join together two strings.

{{% notice blue Example "rocket" %}}
`"Launch" + "Code"` evaluates to `"LaunchCode"`
{{% /notice %}}

Let's compare `+` used with numbers to `+` used with strings.

{{% notice blue Example "rocket" %}}
```javascript
console.log(1 + 1);
console.log("1" + "1");
```

**Console Output**

```console
2
11
```
{{% /notice %}}

This example demonstrates that **the operator + behaves differently based on the data type of its operands.**

{{% notice orange Warning "rocket" %}}
So far we have only seen examples of operators working with data of like type. For the examples `1 + 1` and `"1" + "1"`, both operands are of type `number` and `string`, respectively.

It is possible, however, to mix types with an expression such as `1 + "1"`. The results of doing so can be unexpected, and at this stage of your coding journey we strongly advise against creating such expressions.

We will explore such "mixed" operations in a later chapter.
{{% /notice %}}

## Compound Assignment Operators

A common programming task is to update the value of a variable in reference to itself.

{{% notice blue Example "rocket" %}}
```javascript
let x = 1;
x = x + 1;

console.log(x);
```

**Console Output**

```console
2
```
{{% /notice %}}

Line 2 may seem odd to you at first, since it uses the value of the variable `x` to update `x` itself. This technique is not only legal in JavaScript (and programming in general) but is quite common. It essentially says, "update `x` to be one more than its current value."

This action is so common, in fact, that it has a shorthand operator, `+=`. The following example has the same behavior as the one above.

{{% notice blue Example "rocket" %}}
```javascript
let x = 1;
x += 1;

console.log(x);
```

**Console Output**

```console
2
```
{{% /notice %}}

The expression `x += 1` is shorthand for `x = x + 1`.

There is an entire family of such shorthand operators, known as **compound assignment operators**.

| Operator name | Shorthand | Meaning |
|---------------|-----------|---------|
| Addition assignment     | `a += b`   | `a = a + b` |
| Subtraction assignment  | `a -= b`   | `a = a - b` |
| Multiplication assignment | `a *= b` | `a = a * b` |
| Division assignment     | `a /= b`   | `a = a / b` |