---
title: "shift and unshift Examples"
date: 2021-10-01T09:28:27-05:00
weight: 7
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.shift()` And `.unshift()` Examples

### `.shift()`

The general syntax for this method is:

```javascript
arrayName.shift()
```

This method removes and returns the FIRST element in an array.

No arguments are placed inside the parentheses `()`.

{{% notice blue Example "rocket" %}}

{{% /notice %}}

```javascript
let arr = ['a', 'b', 'c', 'd', 'e'];

arr.shift();

console.log(arr);
```

**Output**

```console
'a'
['b', 'c', 'd', 'e']
```

### `.unshift()`

The general syntax for this method is:

```javascript
arrayName.unshift(item1, item2, ...)
```

This method adds one or more items to the START of an array and returns the
new length.

The new items may be of any data type.

{{% notice blue Example "rocket" %}}
```javascript
let arr = ['a', 'b', 'c'];

arr.unshift('hello', 121);

console.log(arr);
```

**Output**

```console
5
['hello', 121, 'a', 'b', 'c']
```
{{% /notice %}}