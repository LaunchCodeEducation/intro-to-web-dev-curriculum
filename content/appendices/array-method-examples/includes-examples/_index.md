---
title: "includes Example"
date: 2021-10-01T09:28:27-05:00
weight: 2
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.includes()` Example

The general syntax for this method is:

```javascript
arrayName.includes(item)
```

This method checks if an array contains the item specified in the
parentheses `()`, and returns `true` or `false`.

{{% notice blue Example "rocket" %}}
```javascript
let charles = [1, 7, 5, 9, 5];
let otherArr = ['hello', 'world!'];

console.log(charles.includes(5));

console.log(otherArr.includes('hi'));
```

**Output**

```console
true
false
```
{{% /notice %}}