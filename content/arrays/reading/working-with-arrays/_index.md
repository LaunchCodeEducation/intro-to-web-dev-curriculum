---
title: "Working With Arrays"
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

## Bracket Notation and Index

As previously discussed, arrays are an ordered collection where each item can be accessed via index. Similar to strings, an **index** in an
array is the number order given to items. Individual items can be accessed using bracket notation (`array[index]`).
Indexes are zero-based, going from `0` to `array.length-1`.

{{% notice blue Example "rocket" %}}
Use bracket notation and index to access items in an array.

```javascript
let programmingLanguages = [
    "JavaScript", // index 0
    "Python",     // index 1
    "Java",       // index 2
    "C#"          // index 3
];
console.log(programmingLanguages[0]);
console.log(programmingLanguages[3]);

// What will happen when index 4 is requested?
console.log(programmingLanguages[4]);
```

**Console Output**

```console
JavaScript
C#
undefined
```
{{% /notice %}}

Notice above that `undefined` was printed out when index 4 was referenced. `undefined` is returned when you request an index
that the array does not contain.

{{% notice blue Note "rocket" %}}
**undefined** is a special value in JavaScript that means no value has been assigned. We will discuss `undefined` more later in the class.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
`undefined` will be returned for any index that is outside of the array's index range.

```javascript
let programmingLanguages = ["JavaScript", "Python", "Java", "C#"];
console.log(programmingLanguages[-1]);
console.log(programmingLanguages[100]);
```

**Console Output**

```console
undefined
undefined
```
{{% /notice %}}

## Arrays are Mutable

In programming, mutability refers to what happens when you attempt to change a value. Remember that strings are immutable, meaning that any change
to a string results in a new string being created. In contrast, arrays are **mutable**, meaning that individual items in
an array can be edited without a new array being created.

{{% notice blue Example "rocket" %}}
Update an item in an array using bracket notation and index.

```javascript
let javaScriptFrameworks = ["React", "Angular", "Ember"];
console.log(javaScriptFrameworks);

// Set the value of index 2 to be "Vue"
javaScriptFrameworks[2] = "Vue";

// Notice the value at index 2 is now "Vue"
console.log(javaScriptFrameworks);
```

**Console Output**

```console
[ 'React', 'Angular', 'Ember' ]
[ 'React', 'Angular', 'Vue' ]
```
{{% /notice %}}