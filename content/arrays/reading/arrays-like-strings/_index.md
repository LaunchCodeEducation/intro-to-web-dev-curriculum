---
title: "Arrays Are Like Strings"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Arrays are similar to strings, but are a more general collection type. Like
strings, **arrays** are a sequence of values that can be accessed via an
ordered index. Unlike strings, arrays can store data of any type.

The figure below demonstrates an array of named languages. The array contains
four strings, each of those values has an index position.

![A label, languages, pointing to an array that contains "Python" at index 0, "C#" at index 1, "Java" at index 2, and "JavaScript" at index 3.](pictures/Arrays-are-like-strings.png?classes=border)

## Declaring an Array

Programmers use multiple ways to declare a new array. The simplest way is to
use **array literal** notation `[]`. Anything enclosed in the square brackets
will be *items* in the array. Each item should be followed by a comma `,`. If
there are no items inside the brackets, then the array is considered empty.

```javascript
let emptyArray = [];

let programmingLanguages = ["JavaScript", "Python", "Java", "C#"];
```

Array items can also be declared on multiple lines.

```javascript
let javaScriptFrameworks = [
    "React",
    "Angular",
    "Ember",
    "Vue"
];
```

## Array Length

To check the length of an array, use the `length` property, just like with
strings. JavaScript array length is NOT fixed, meaning you can add or remove
items dynamically.

{{% notice blue Note "rocket" %}}
In other languages, such as Java and C#, arrays are of a static length requiring the
length of the array to be declared upon creation.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
Print out the length of two arrays.

```javascript
let emptyArray = [];
console.log(emptyArray.length);

let programmingLanguages = ["JavaScript", "Python", "Java", "C#"];
console.log(programmingLanguages.length);
```

**Console Output**

```console
0
4
```
{{% /notice %}}

## Varying Data Types

JavaScript arrays can hold a mixture of values of any type. For example, you
can have an array that contains strings, numbers, and booleans.

```javascript
let grabBag = ["A string value", true, 99, 105.5];
```

{{% notice blue Note "rocket" %}}
It’s rare that you would store data of multiple types in the same array, because grouped data is usually the same type. In other languages, such as Java and C#, all items in an array have to be of the same type.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is the length of the two arrays?

*Hint: look closely at the quotes in the classes array.*

```javascript
let classes = ["science, computer, art"];

let teachers = ["Jones", "Willoughby", "Rhodes"];
```

How can you change the `classes` array declaration to have the same number of items as the `teachers` array?

<!-- Solution: Encapsulate all index items with double quotes, similar to the teachers array -->
{{% /notice %}}