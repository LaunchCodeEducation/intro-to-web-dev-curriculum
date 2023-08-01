---
title: "Bracket Notation"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Understanding strings as sequential collections of characters gives us much more than just a mental model of how they are structured. JavaScript provides a rich collection of tools---including special syntax and operations---that allows us to work with strings.

**Bracket notation** is the special syntax that allows us to access the individual characters that make up a string. To access a character, we use the syntax `someString[i]`, where `i` is the **index** of the character we want to access. String indices are integers representing the position of a character within a given string, and they start at 0. Thus, the first character of a string has index 0, the second has index 1, and so on.

Consider the string `"JavaScript"`. The `"J"` has index 0, the first `"a"` has index 1, `"v"` has index 2, and so on.

![The string "JavaScript" with indices labeled below each letter](pictures/string-indices.png?classes=border)

An expression of the form `someString[i]` gives the character at index `i`.

{{% notice blue Example "rocket" %}}
This program prints out the initials of the person's name.

```javascript {linenos=true}
let jsCreator = "Brendan Eich";
let firstInitial = jsCreator[0];
let lastInitial = jsCreator[8];

let outputStr = "JavaScript was created by somebody with initials " + 
   firstInitial + "." +
   lastInitial + ".";

console.log(outputStr);
```

**Console Output**

```console
JavaScript was created by somebody with initials B.E.
```
{{% /notice %}}

What happens if we try to access an index that doesn't exist, for example -1 or an index larger than the length of the string?

{{% notice blue "Try It!" "rocket" %}}
```javascript {linenos=true}
let jsCreator = "Brendan Eich";

console.log(jsCreator[-1]);
console.log(jsCreator[42]);
```
{{% /notice %}}

{{% notice green Question "rocket" %}}
What does an expression using bracket notation evaluate to when the index is invalid (the index does not correspond to a character in the string)?
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
If `phrase = 'Code for fun'`, then `phrase[2]` evaluates to:

1. `"o"`
2. `"d"`
3. `"for"`
4. `"fun"`

<!-- Solution: "d" -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Which of the following returns `true` given `myStr = 'Index'`? Choose all correct answers.

1. `myStr[2] === 'n';`
2. `myStr[4] === 'x';`
3. `myStr[6] === ' ';`
4. `myStr[0] === 'I';`

<!-- Solution: answers 2 and 4 return true, the others return false -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is printed by the following code?

```javascript {linenos=true}
let phrase = "JavaScript rocks!";
console.log(phrase[phrase.length - 8]);
```

1. `"p"`
2. `"i"`
3. `"r"`
4. `"t"`

<!-- Solution: t -->
{{% /notice %}}