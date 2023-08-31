---
title: "concat Examples"
date: 2021-10-01T09:28:27-05:00
weight: 1
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.concat()` Examples

The general syntax for this method is:

```bash
arrayName.concat(otherArray1, otherArray2, ...)
```

This method adds the elements of one array to the end of another. The new array
must be stored in a variable or printed to the screen, because ``concat`` does
NOT alter the original arrays.

{{% notice blue Example "rocket" %}}
```javascript
let arr = [1, 2, 3];
let otherArray = ['M', 'F', 'E'];
let newArray = [];

newArray = arr.concat(otherArray);
console.log(newArray);

newArray = otherArray.concat(arr);
console.log(newArray);

console.log(arr.concat(otherArray, arr));

console.log(arr);
```

**Output**

```console
[1, 2, 3, 'M', 'F', 'E']
[ 'M', 'F', 'E', 1, 2, 3 ]
[ 1, 2, 3, 'M', 'F', 'E', 1, 2, 3 ]
[1, 2, 3]
```
{{% /notice %}}