---
title: "Running Programs in the Terminal"
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

Quickly navigating through our filesystems is just one benefit of using the terminal for programmers.
We can also quickly run our code inside of the terminal to see the outputs.

The commands used to run a program in the terminal vary widely based on type of program you want to run.
However, no matter what language you are coding in, the documentation will include, in some format, ways to run the program in the terminal. 

{{% notice blue Example "rocket" %}}
So far, in this class, we have been running our programs by typing `node <file-name>` into our terminal.
{{% /notice %}}

Let's say there is an error in our program like an infinite loop. How then do we get it to stop running so we can go back and fix our code?

In many cases, typing *ctrl+c* into the terminal will stop a process that is currently running. However, if that doesn't work, the `exit` command can also stop a currently running process.

There are also many other programs and software designed to run within the terminal or cli specifically. Below is a fun example.

Neofetch is a CLI tool designed to display information about your system. It provides a logo of your operating system in addition to other hardware specifications.

![Neofetch program run as example](pictures/neofetch-example.png?classes=border)