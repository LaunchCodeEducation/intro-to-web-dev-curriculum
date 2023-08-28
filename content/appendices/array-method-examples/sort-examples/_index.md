---
title: "sort Examples"
date: 2021-10-01T09:28:27-05:00
weight: 9
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## ``.sort()`` Examples

The general syntax for this method is:

```javascript
arrayName.sort()
```

This method arranges the elements of an array into increasing order.  For
strings, this means alphabetical order.  HOWEVER, the results are not always
what we expect.

{{% notice blue Example "rocket" %}}
Alphabetical order?

```javascript
let letters = ['f', 'c', 'B', 'X', 'a'];

letters.sort();
console.log(letters);
```

**Output**

```console
[ 'B', 'X', 'a', 'c', 'f' ]
```
         
From the alphabet song, we know that 'a' comes before 'B' (and certainly before
'X'), but JavaScript treats capital and lowercase letters differently.  The
default sort order places capital letters before lowercase.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```javascript
let mixed = ['a', 'A', 20, 40];

mixed.sort();
console.log(mixed);
```

**Output**

```console
[ 20, 40, 'A', 'a' ]
```

When numbers and strings are sorted, the default order places numbers before
all letters.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
Numerical sorting.

```javascript
let numbers = [2, 8, 10, 400, 30];

numbers.sort();
console.log(numbers);
```

   **Output**

```console
[ 10, 2, 30, 400, 8 ]
```

Here JavaScript gets truly bizarre. How is 8 larger than 400?

When JavaScript sorts, it converts all entries into strings by default. Just
like 'Apple' comes before 'Pear' because 'A' comes before 'P', the string '400'
begins with a '4', which comes before any string starting with an '8'. Looking
only at the first digit in each number, we see the expected progression
(1, 2, 3, 4, 8).

Later in this course, we will explore ways to fix this issue and correctly sort
numerical arrays.
{{% /notice %}}