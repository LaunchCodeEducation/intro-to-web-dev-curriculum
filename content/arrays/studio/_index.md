---
title: "Studio: Strings and Arrays"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Strings are **ordered collections** of *characters*, which are strings of
length 1. The characters in a string can be accessed using
**bracket notation**.

Arrays are ordered collections of items, which can be strings, numbers,
other arrays, etc. The items/elements/entries stored in an array can be
accessed using bracket notation.

Strings are **immutable**, whereas arrays can be changed.

Strings and arrays have **properties** and **methods** that allow us to easily
perform some useful actions.


## String Modification

Use string methods to convert a word into pseudo-pig latin.

1. Remove the first three characters from a string and add them to the end. Ex: `'LaunchCode'` becomes `'nchCodeLau'`. Use a template literal to print the original and modified string in a descriptive phrase.
1. Modify your code to accept user input. Query the user to enter the number of letters that will be relocated.
1. Add validation to your code to deal with user inputs that are longer than the word. In such cases, default to moving 3 characters. Also, the template literal should note the error.

## Array and String Conversion

<!-- TODO: Bring in Tested Code section from old textbook. In the meantime it still links to old book. -->

{{% notice blue Note "rocket" %}}
The starter code for this section contains unit tests.  You will see a lot of new code in the starter code. The directions will tell you which function to work in. Look for the `TODO` and `NOTE` comments for guidance and direction. The [Tested Code](https://education.launchcode.org/intro-to-professional-web-dev/appendices/tested-code.html#tested-code) page provides more information and tips for working inside code like this.

Open the `javascript-projects/arrays/studio/array-string-conversion` directory and run `npm i` to install the required dependences.
{{% /notice %}}

The `split` and `join` methods convert back and forth between strings
and arrays. Use **delimiters** as reference points to split a string into an
array, then modify the array and convert it back to a printable string.

1. For a given string, use the `includes` method to check to see if the words are separated by commas (`,`), semicolons (`;`), or just spaces.

1. Use the `reverseCommas()` function to code the following.  If the string uses commas to separate the words, `split` it into an array, reverse the entries, and then `join` the array into a new comma-separated string. For example, `"up,to,code,fun"` becomes `"fun,code,to,up"`.
   
1. Use the `semiDash()` function to code the following. If the string uses semicolons to separate the words, `split` it into an array, alphabetize the entries, and then `join` the array into a new hyphen-separated string. For example, `"up;to;code;fun"` becomes `"code-fun-to-up"`.

1. Use the `reverseSpace()` function to code the following. If the string uses spaces to separate the words, `split` it into an array, reverse alphabetize the entries, and then `join` the array into a new space-separated string. For example, `"to code up fun"` becomes `"up to fun code"`.

1. Use the `commaSpace()` function to code the following.  *Consider*: What if the string uses 'comma spaces' (, ) to separate the list? Modify your code to produce the same result as part "b", making sure that the extra spaces are NOT part of the final string.

## Bonus Mission: Multi-dimensional Arrays

Arrays can store other arrays!

1. The cargo hold in our shuttle contains several smaller storage spaces. Use `split` to convert the following strings into four cabinet arrays. Alphabetize the contents of each cabinet.
    - `"water bottles, meal packs, snacks, chocolate"`
    - `"space suits, jet packs, tool belts, thermal detonators"`
    - `"parrots, cats, moose, alien eggs"`
    - `"blankets, pillows, eyepatches, alarm clocks"`
1. Initialize a `cargoHold` array and add the cabinet arrays to it. Print `cargoHold` to verify its structure.
1. Query the user to select a cabinet (0-3) in the `cargoHold`.
1. Use bracket notation and a template literal to display the contents of the selected cabinet. If the user entered an invalid number, print an error message instead.
1. *Bonus to the Bonus*: Modify the code to query the user for BOTH a cabinet in `cargoHold` AND a particular item. Use the `include` method to check if the cabinet contains the selected item, then print `"Cabinet ____DOES/DOES NOT contain ____."`