---
title: "reverse Example"
date: 2021-10-01T09:28:27-05:00
weight: 6
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.reverse()` Example

The general syntax for this method is:

```javascript
arrayName.reverse()
```

This method is straightforward - it reverses the order of the elements in the
array.

No arguments are placed inside the parentheses `()`.

{{% notice blue Example "rocket" %}}
```javascript
let arr = ['At', 'banana', 'orange', 'apple', 'zoo'];

arr.reverse();
console.log(arr);
```
         
**Output**

```console

[ 'zoo', 'apple', 'orange', 'banana', 'At' ]
```
{{% /notice %}}