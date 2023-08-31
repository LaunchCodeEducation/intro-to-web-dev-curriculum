---
title: "join Examples"
date: 2021-10-01T09:28:27-05:00
weight: 4
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.join()` Examples

The general syntax for this method is:

```javascript
arrayName.join('connector')
```

`join` combines all the elements of an array into a string. The *connector*
determines the string that "glues" the array elements together.

{{% notice blue Example "rocket" %}}
```javascript
let arr = [1, 2, 3, 4];
let words = ['hello', 'world', '!'];
let newString = '';

newString = arr.join("+");
console.log(newString);

newString = words.join("");
console.log(newString);

newString = words.join("_");
console.log(newString);
```

**Output**

```console

1+2+3+4
helloworld!
hello_world_!
```
{{% /notice %}}