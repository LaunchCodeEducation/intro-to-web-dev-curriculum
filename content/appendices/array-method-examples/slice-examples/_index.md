---
title: "slice Examples"
date: 2021-10-01T09:28:27-05:00
weight: 8
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.slice()` Examples

The general syntax for this method is:

```javascript
arrayName.slice(starting index, ending index)
```

This method copies a range of elements from one array into a new array. `slice`
does NOT change the original array, but returns a new array.

The ending index is optional.  If it is left out, `slice` returns a new array
that includes everything from the starting index to the end of the original
array.

If both indices are used, the new array contains everything from the starting
index up to, but NOT including the ending index.

{{% notice blue Example "rocket" %}}
```javascript
let arr = ['a', 'b', 'c', 'd', 'e'];

arr.slice(2);

arr.slice(1,4);

console.log(arr);
```

**Output**

```console
[ 'c', 'd', 'e' ]
[ 'b', 'c', 'd' ]
['a', 'b', 'c', 'd', 'e']
```
{{% /notice %}}