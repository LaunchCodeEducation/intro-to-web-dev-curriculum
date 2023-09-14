---
title: "indexOf Examples"
date: 2021-10-01T09:28:27-05:00
weight: 3
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.indexOf()` Examples

The general syntax for this method is:

```javascript
arrayName.indexOf(item)
```

This method returns the index of the FIRST occurence of an item in the array.
If the item is not in the array, -1 is returned.

{{% notice blue Example "rocket" %}}
```javascript
let charles = [1, 7, 5, 9, 5];
let otherArray = ['hello', 'world!'];

console.log(charles.indexOf(5));

console.log(otherArray.indexOf('hi'));
```

**Output**

```console
2
 -1
```
{{% /notice %}}