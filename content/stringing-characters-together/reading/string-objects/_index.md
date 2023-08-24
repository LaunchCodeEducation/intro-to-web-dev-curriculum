---
title: "Strings as Objects"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Beyond bracket notation, there are many other tools we can use to work with strings. Talking about these tools requires some new terminology.

## Object Terminology

In JavaScript, strings are objects, so to understand how we can use them in our programs, we must first understand some basics about objects.

An **object** is a collection of related data and operations. An operation that can be carried out on an object is known as a **method**. A piece of data associated with an object is known as a **property**.

{{% notice blue Example "rocket" %}}
Suppose we had a `square` object in JavaScript. (While no such object is built into JavaScript, we will learn how we could make one in a later chapter.)

Since a square has four sides of the same length, it should have a property to represent this length. This property could be called `length`. For a given square, it will have a specific value, such as 4.

Since a square has an area, it should have a method to calculate the area. This method could be called `area`, and it should calculate the area of a square using its `length` property.
{{% /notice %}}

You can think of methods and properties as functions and variables, respectively, that "belong to" an object. Properties and methods are accessed using **dot notation**, which dictates that we use the object name, followed by a `.`, followed by the property or method name. When using a method, we must also use parentheses as we do when calling regular functions.

{{% notice blue Example "rocket" %}}
Returning to the `square` example, we can access its length by typing `square.length`.

We can calculate the area by calling `square.area()`.
{{% /notice %}}

Referencing `length` or `area` by itself in code *does not* give you the value of `square.length` or carry out the calculation in `square.area()`. It does not make sense to refer to a property or method without also referring to the associated object. Typing simply `length` or `area()` is ambiguous. There might be multiple squares, and it would be unclear which one you were asking about.

{{% notice blue Example "rocket" %}}
We have already encountered one object, the built-in object ``console``, which we use to output messages.

```javascript
console.log(typeof console);
```

**Console Output**

```console
object
```

JavaScript reports that the type of `console` is indeed `object`.

When calling `console.log`, we are calling the `log` method of the `console` object.
{{% /notice %}}

We will learn quite a bit more about objects in this course, including how to
use objects to create your own custom data types. This powerful JavaScript
feature allows us to bundle up data and functionality in useful, modular ways.

## Strings Are Objects

The fact that strings are objects means that they have associated data and operations, or properties and methods as we will call them from now on.

Every string that we work with will have the same properties and methods. The most useful string property is named `length`, and it tells us how many characters are in a string.

{{% notice blue Example "rocket" %}}
```javascript {linenos=true}
let firstName = "Grace";
let lastName = "Hopper";

console.log(firstName, "has", firstName.length, "characters");
console.log(lastName, "has", lastName.length, "characters");
```

**Console Output**

```console
Grace has 5 characters
Hopper has 6 characters
```
{{% /notice %}}

Every string has a `length` property, which is an integer.

The `length` property is the only string property that we will use, but there are many useful string methods. We will explore these in depth in the section :ref:`string-methods`, but let's look at one now to give you an idea of what's ahead.

The `toLowerCase()` string method returns the value of its string in all lowercase letters. Since it is a method, we must precede it with a specific string in order to use it.

{{% notice blue Example "rocket" %}}
```javascript
let nonprofit = "LaunchCode";

console.log(nonprofit.toLowerCase());
console.log(nonprofit);
```

**Console Output**

```console
launchcode
LaunchCode
```
{{% /notice %}}

Notice that `toLowerCase()` does not alter the string itself, but instead *returns* the result of converting the string to all lowercase characters. In fact, it is not possible to alter the characters within a string, as we will now see.

## Check Your Understanding

{{% notice green Question "rocket" %}}
Given `word = 'Rutabaga'`, why does `word.length` return the integer 8, but `word[8]` is `undefined`?
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is the length of `location`?

```javascript
cityName = "Vienna";
stateName = "Virginia";
location = cityName + ", " +  stateName;

console.log(location.length);
```

1. 16
1. 17
1. 15
1. 14

<!-- Solution: 16 -->
{{% /notice %}}