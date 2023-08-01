---
title: "String Immutability"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 4
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

If an object cannot be changed, we say that it is **immutable**. Strings are
immutable, which means we cannot change the individual characters within a
given string. While we can access individual characters using bracket
notation, attempting to change individual characters simply does not work.

{{% notice blue Example "rocket" %}}
```javascript {linenos=true}
let nonprofit = "Launchcode";

console.log(nonprofit);
nonprofit[6] = "C";
console.log(nonprofit);
```

**Console Output**

```console
Launchcode
Launchcode
```
{{% /notice %}}

We attempted to change the value of the character at index 6 from `'c'` to `'C'`, by using an assignment statement along with bracket notation on line 4 (perhaps to align with official LaunchCode branding guidelines). However, this change clearly did not take place. In many programming languages strings are immutable, and while trying to change a string in some languages results in an error, JavaScript simply ignores our request to alter a string.

It is important to notice that immutability applies to string *values* and not string variables.

{{% notice blue Example "rocket" %}}
We can set a variable containing a string to a different value.

```javascript
let nonprofit = "Launchcode";
nonprofit = "LaunchCode";

console.log(nonprofit);
```

**Console Output**

```console
LaunchCode
```
{{% /notice %}}

In this example, the change made on line 2 is carried out. The difference between this example and the one above is that here we are modifying the value that the variable is storing, and not the string itself. Using our visual analogy of a variable as a label that "points at" a value, the second example has the following effect:

![A variable, nonprofit, pointing at "LaunchCode" with a lowercase-c.](pictures/string-var-reassignment.png?classes=border)

When the value of a variable storing a string is changed, the variable then points to a new value, with the old value remaining unchanged.

## Check Your Understanding

{{% notice green Question "rocket" %}}
Given `pet = 'cat'`, why do the statements `console.log(pet + 's');` and `pet += 's';` NOT violate the immutability of strings?

<!-- Solution: This example is simply adding content to an existing string. If you console.log the variable pet it will result in 'cat' -->
{{% /notice %}}