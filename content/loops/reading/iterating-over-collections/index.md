---
title: "Iterating Over Collections"
date: 2023-08-28T09:21:11-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

One of the most common uses of a `for` loop is to carry out a task once for each item in a collection. We have learned about two types of collections, strings and arrays. When using a loop with a collection in this way, we say that the loop *iterates over* the collection.

## Iterating Over Strings

The following example prints each of the characters of the string `"LaunchCode"` on a separate line.

{{% notice blue "Example" "rocket" %}}
   ```js {linenos=table}
   let name = "LaunchCode";

   for (let i = 0; i < name.length; i++) {
      console.log(name[i]);
   }
   ```

   **Console Output**

   ```console
   L
   a
   u
   n
   c
   h
   C
   o
   d
   e
   ```
{{% /notice %}}

Since `name.length` is 10, the loop executes once each for the values of `i` from 0 to 9. The loop body, `console.log(name[i]);`, will print `name[i]` each time. In each case, `name[i]` is one of the characters of `name`.

{{% notice blue "Example" "rocket" %}}

   In your copy of `javascript-projects`, open up `loops/chapter-examples`. Inside you will find `for-Loop-Practice-With-Strings.js`. In this file, try writing a program that prints each character of your name on a different line.

   ```js
   // create a string variable containing your name

   // write a for loop that prints each character in your name on a different line
   ```
{{% /notice %}}

## Iterating Over Arrays

The following example prints each of the programming languages in the array `languages` on a separate line.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=table}
   let languages = ["JS", "Java", "C#", "Python"];

   for (let i = 0; i < languages.length; i++) {
      console.log(languages[i]);
   }
   ```

   **Console Output**

   ```console
   JS
   Java
   C#
   Python
   ```

{{% /notice %}}

Similar to the string example, this loop executes 4 times because
`languages.length` is 4. For each iteration, `languages[i]` is one of the
items in the array and the given language is printed.

{{% notice blue "Example" "rocket" %}}
   Inside `chapter-examples` in the `loops` directory in `javascript-projects`, you will find `for-Loop-Practice-With-Arrays.js`. In this file, try writing a program that prints the name of each member of your family on a different line.

   ```js {linenos=table}
   // create an array variable containing the names

   // write a for loop that prints each name on a different line
   ```
{{% /notice %}}