---
title: "Exercises: Git"
date: 2023-09-26T13:52:51-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

We will use our new terminal powers to move through the Git exercises.

1. In whichever directory you are keeping your coursework *outside of javascript-projects*, make a new directory called `Git-Exercises` using the `mkdir` command. You want to make sure this is outside of `javascript-projects` because it will cause an issue if you try and make a new Git repository inside an existing one.

   {{% expand "Check your solution"%}}

   ```console
   My-Computer:my-coursework myusername$ mkdir Git-Exercises
   ```

   {{% /expand %}}

1. Inside the `Git-Exercises` directory, initialize a new Git repository using `git init`.
1. Use `git branch` to check the default branch name. If necessary, change the
   branch name to `main`.
1. Add a file called `exercises.txt` using the `touch` command in the terminal.

   {{% expand "Check Your Solution" %}}
   
   ```console
   My-Computer:Git-Exercises myusername$ touch exercises.txt
   ```

   {{% /expand %}}

1. Commit your local changes using the `git commit` procedures.
1. Add `"Hello World!"` to the file called `exercises.txt`.
1. Commit your local changes following the same steps that you used for step 5.
1. Run the `git log` command. Take a screenshot of the result. Make note of
   what you see!

   {{% expand "Check your solution" %}}

   ```console
   My-Computer:Git-Exercises myusername$ git log
   commit 00000000000000000000000000000000000000000
   Author: Me <myemail>
   Date:   Jan 1 01:01:01 2021

      Wrote Hello World
   ```
   
   {{% /expand %}}

