---
title: "push and pop Examples"
date: 2021-10-01T09:28:27-05:00
weight: 5
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.push()` And `.pop()` Examples

### `.push()`

The general syntax for this method is:

```javascript
arrayName.push(item1, item2, ...)
```

This method adds one or more items to the END of an array and returns the
new length.

The new items may be of any data type.

{{% notice blue Example "rocket" %}}
```javascript
let arr = ['a', 'b', 'c'];

console.log(arr.push('d', 'f', 42));

console.log(arr);
```

**Output**

```console
6
['a', 'b', 'c', 'd', 'f', 42]
```
{{% /notice %}}

### `.pop()`

The general syntax for this method is:

```javascript
arrayName.pop()
```

This method removes and returns the LAST element in an array.

No arguments are placed inside the parentheses `()`.

{{% notice blue Example "rocket" %}}
```javascript
let arr = ['a', 'b', 'c', 'd', 'e'];

arr.pop();

console.log(arr);
```

**Output**

```console
e
['a', 'b', 'c', 'd']
```
{{% /notice %}}