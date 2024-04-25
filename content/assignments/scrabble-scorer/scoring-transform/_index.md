---
title: "Task 3: Transform Scrabble Scoring"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas 
reviewerGitHub: icre8FreeCode 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Currently, the software contains the data structure below for the traditional
Scrabble scoring algorithm. Take a few moments to review how the
`oldPointStructure` object relates a point value to a letter.

```js {linenos=table}
   const oldPointStructure = {
      1: ['A', 'E', 'I', 'O', 'U', 'L', 'N', 'R', 'S', 'T'],
      2: ['D', 'G'],
      3: ['B', 'C', 'M', 'P'],
      4: ['F', 'H', 'V', 'W', 'Y'],
      5: ['K'],
      8: ['J', 'X'],
      10: ['Q', 'Z']
   };
```

The *keys* of `oldPointStructure` are the Scrabble points, and the
*values* are arrays of letters. All letters in the array have the Scrabble
point value equal to the key. For example, `'A'` and `'R'` are worth 1,
`'K'` is worth 5, and `'J'` is worth 8.

To find the point value for a letter with the old format, the program must
iterate over each key in `oldPointStructure` and then check if the letter is
inefficient*.

{{% notice green "Tip" "rocket" %}}
Think about this for a second. The scoring action takes in letters in a word as input
and outputs numerical point values. 

We can improve our program by rewriting the data structure to better fit the action
we want to take. Keep this idea in mind as you go on to code your own
applications.

{{% /notice %}}

It would improve the performance of the program to create a `newPointStructure` object that has 26 keys,
one for each letter. The value of each key will be the Scrabble point value.

{{% notice blue Note "rocket" %}}
The `newPointStructure` object will be created and tested during Task 4. Below are examples of what the new object storage will look like, in addition to testing the new object itself. You will not be able to test the `newPointStructure` object until Task 4!
{{% /notice %}}

Examples of the new key storage:

1. `a` is worth `1`
1. `b` is worth `3`
1. `c` is worth `3`
1. `j` is worth `8`

In `newPointStructure`, the letters themselves are keys, so a *single* search
will identify a point value. 

{{% notice blue "Example" "rocket" %}}
Example of `newPointStructure` object usage.

```js
console.log("Scrabble scoring values for");
console.log("letter a: ", newPointStructure.a);
console.log("letter j: ", newPointStructure.j);
console.log("letter z: ", newPointStructure["z"]);
```

**Console Output**

```console
Scrabble scoring values for
letter a:  1
letter j:  8
letter z:  10
```
{{% /notice %}}