---
title: "Exercises: Strings"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

## Part One

1. The `length` method returns how many characters are in a string. However, the method will NOT give us the length of a number. If `num = 1001`, `num.length` returns `undefined` rather than 4.

- Use type conversion to print the length (number of digits) of an integer.
- Print the number of digits in a DECIMAL value (e.g. `num = 123.45` has 5 digits but a length of 6).
  - Modify your code to print out the length of a decimal value EXCLUDING the period.

- What if `num` could be EITHER an integer or a decimal?  Add an `if/else` statement so your code can handle both cases.  (Hint: Consider the `indexOf()` or `includes()` string methods).

   {{% expand "Check Your Solution" %}}
   ```javascript
   if (String(num).includes('.')){
   console.log(String(num).length-1);
   } else {
   console.log(String(num).length);
   }
   ```
   {{% /expand %}}

## Part Two

1. Remember, strings are *immutable*. Consider a string that represents a strand of DNA: `dna = " TCG-TAC-gaC-TAC-CGT-CAG-ACT-TAa-CcA-GTC-cAt-AGA-GCT    "`. There are some typos in the string that we would like to fix:

- Use the `trim()` method to remove the leading and trailing whitespace,
and then print the results.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let dna = " TCG-TAC-gaC-TAC-CGT-CAG-ACT-TAa-CcA-GTC-cAt-AGA-GCT    ";
   let newString = dna.trim();
   console.log(newString);
   ```
   {{% /expand %}}

- Change all of the letters in the dna string to UPPERCASE and print the
result.
- Note that if you try `console.log(dna)` after applying the methods, the
original, flawed string is displayed. To fix this, you need to
*reassign* the changes back to `dna`. Apply these fixes to your
code so that `console.log(dna)` prints the DNA strand in UPPERCASE
with no whitespace.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let dna = " TCG-TAC-gaC-TAC-CGT-CAG-ACT-TAa-CcA-GTC-cAt-AGA-GCT    ";
   dna = dna.trim().toUpperCase();
   console.log(dna);
   ```
   {{% /expand %}}

2. Let's use string methods to do more work on the DNA strand:

- Replace the sequence `'GCT'` with `'AGG'`, and then print the altered strand.
    
   {{% expand "Check Your Solution" %}}
   ```javascript
   dna = dna.replace('GCT','AGG');
   console.log(dna);
   ```
   {{% /expand %}}

- Look for the sequence `'CAT'` with `indexOf()`. If found print, `'CAT found'`, otherwise print, `'CAT NOT found'`.
- Use `slice()` to print out the fifth set of 3 characters (called a **codon**) from the DNA strand.
    
   {{% expand "Check Your Solution" %}}
   ```javascript
   console.log(dna.slice(16,19));
   ```
   {{% /expand %}}

- Use a template literal to print, `"The DNA strand is ___ characters long."`
- Just for fun, apply methods to `dna` and use another template literal to print, `'taco cat'`.
    
   {{% expand "Check Your Solution" %}}
   ```javascript
   console.log(`${dna.slice(4,7).toLowerCase()}o ${dna.slice(dna.indexOf('CAT'),dna.indexOf('CAT')+3).toLowerCase()}`);
   ```
   {{% /expand %}}

## Part Three

1. If we want to turn the string `'JavaScript'` into `'JS'`, we might try `.remove()`. Unfortunately, there is no such method in JavaScript. However, we can use our cleverness to achieve the same result.

- Use string concatenation and two `slice()` methods to print `'JS'` from `'JavaScript'`.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let language = 'JavaScript';
   console.log(language.slice(0,1)+language.slice(4,5));
   ```
   {{% /expand %}}

- Without using `slice()`, use method chaining to accomplish the same thing.
- Use bracket notation and a template literal to print, ``"The abbreviation for 'JavaScript' is 'JS'."``

   {{% expand "Check Your Solution" %}}
   ```javascript
   console.log(`The abbreviation for '${language}' is '${initials}'.`)
   ```
   {{% /expand %}}

- Just for fun, try chaining 3 or more methods together, and then print the result.

2. Some programming languages (like Python) include a `title()` method to
   return a string with Every Word Capitalized (e.g. `'title case'.title()`
   returns `Title Case`).  JavaScript has no `title()` method, but that
   won't stop us! Use the string methods you know to print `'Title Case'`
   from the string `'title case'`.