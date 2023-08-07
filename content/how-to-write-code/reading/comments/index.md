---
title: "Comments"
date: 2023-07-13T14:00:03-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

As programs get bigger and more complicated, they get more difficult to read.
Good programmers try to make their code understandable to others, but it is
still tricky to look at a large program and figure out what it is doing and
why.

Best practice encourages us to add notes to our programs, which clearly
explain what the program is doing. These notes are called *comments*.

A **comment** is text within a program intended only for a human reader---it is
completely ignored by the compiler or interpreter. In JavaScript, the `//`
token starts a comment, and the rest of the line gets ignored. For comments
that stretch over multiple lines, the text falls between the symbols
`/*   */`.

## Experiment with Comments

1. On your own computer, in `javascript-projects`, locate the `how-to-write-code` folder. Within that folder, you will find an example called `Comments.js`. *You should use the terminal to do so.* Here are the steps:
   1. Use `cd` to locate `javascript-projects`. If your work is in `LaunchCode/Unit1`, then the command would be `cd LaunchCode/Unit1`. Run the command, `ls`, to make sure that you have found `javascript-projects`.
   1. To navigate inside the `how-to-write-code` folder, use the command `cd javascript-projects/how-to-write-code`.
   1. Open up the required example in Visual Studio Code by running the command, `code Comments.js`.
1. You are ready to add and remove comments! Here is where the code starts out at:

   ```js {linenos=table}
      // This demo shows off comments!

      // console.log("This does not print.");

      console.log("Hello, World!"); // Comments do not have to start at the beginning of a line.

      /* Here is how
      to have
      multi-line
      comments. */

      console.log("Comments make your code more readable by others.");
   ```

1. Try removing or un-commenting some code first. Then try adding both a single-line and multi-line comment. 

   {{% notice green "Tip" "rocket" %}}
   Remember to run the program, you should use the command, `node comments`.
   {{% /notice %}}

Notice that when you first run the program, it still prints the phrase `Hello,
World!`, but none of the comments appear. Also notice the blank lines left in
the code, which are also ignored by the compiler. Comments and blank lines make
your programs much easier for humans to understand. Use them frequently!