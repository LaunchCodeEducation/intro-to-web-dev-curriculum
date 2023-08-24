---
title: "Template Literals"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 8
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Earlier, we used *concatenation* to combine strings and variables together in
order to create specific output:

{{% notice blue Example "rocket" %}}
```javascript
let name = "Jack";
let currentAge = 9;

console.log("Next year, " + name + " will be " + (currentAge + 1) + ".");
```

**Console Output**

```console
Next year, Jack will be 10.
```
{{% /notice %}}

Unfortunately, this process quickly gets tedious for any output that depends on
multiple variables. Often, concatenation requires multiple test runs of the
code in order to check for syntax errors and proper spacing within the output.
Fortunately, JavaScript offers us a better way to accomplish this process.

**Template literals** allow for the automatic insertion of expressions
(including variables) into strings.

While normal strings are enclosed in single or double quotes (`'` or `"`),
template literals are enclosed in back-tick characters, ``. Within a
template literal, any expression surrounded by `${ }` will be evaluated, with
the resulting value included in the string.

{{% notice blue Example "rocket" %}}
Template literals allow for variables and other expressions to be directly
included in strings.

```javascript
let name = "Jack";
let currentAge = 9;

console.log(`Next year, ${name} will be ${currentAge + 1}.`);
```

**Console Output**

```console
Next year, Jack will be 10.
```
{{% /notice %}}



Besides allowing us to include data in strings in a cleaner, more readable way,
template literals also allow us to easily create multi-line strings without
using string concatenation or special characters.

{{% notice blue Example "rocket" %}}
```javascript {linenos = true}
let poem = `The mind chases happiness.
The heart creates happiness.
The soul is happiness
And it spreads happiness
All-where.

– Sri Chinmoy`;

console.log(poem);
```

**Console Output**

```console
The mind chases happiness.
The heart creates happiness.
The soul is happiness
And it spreads happiness
All-where.

– Sri Chinmoy
```
{{% /notice %}}



{{% notice blue Note "rocket" %}}
The ECMAScript specifications define the standard for JavaScript. The 6th
edition, known as ES2015, added template literals. Not only are template
literals relatively new to JavaScript, but you may encounter
environments---such as older web browsers---where they are not supported.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Mad Libs are games where one player asks the group to supply random words
(e.g. "Give me a verb," or, "I need a color"). The words are substituted
into blanks within a story, which is then read for everyone's amusement. In
elementary school classrooms, giggles and hilarity often ensue. TRY IT!

Refactor the following code to replace the awkward string concatenation with template literals. Be sure to add your own choices for the variables.

```javascript
let pluralNoun = ;
let name = ;
let verb = ;
let adjective = ;
let color = ;

console.log("JavaScript provides a "+ color +" collection of tools — including " + adjective + " syntax and " + pluralNoun + " — that allows "+ name +" to "+ verb +" with strings.")
```
{{% /notice %}}