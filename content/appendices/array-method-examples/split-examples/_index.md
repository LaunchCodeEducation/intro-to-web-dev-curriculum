---
title: "split Examples"
date: 2021-10-01T09:28:27-05:00
weight: 11
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.split()` Examples

The general syntax for this method is:

```javascript
stringName.split('delimiter')
```

`split` is actually a string method, but it complements the array method
`join`.

`split` divides a string into smaller pieces, which are stored in a new
array. The **delimiter** argument determines how the string is broken apart.

{{% notice blue Example "rocket" %}}
```javascript
let numbers = "1,2,3,4";
let word = "Rutabaga";
let phrase = "Bookkeeper of balloons."
let arr = [];

arr = numbers.split(',');  //split the string at each comma.
console.log(arr);

arr = phrase.split(' ');   //split the string at each space.
console.log(arr);

arr = word.split('');      //split the string at each character.
console.log(arr);
```

**Output**

```console
['1', '2', '3', '4']
['Bookkeeper', 'of', 'balloons.']
['R', 'u', 't', 'a', 'b', 'a', 'g', 'a']
```
{{% /notice %}}