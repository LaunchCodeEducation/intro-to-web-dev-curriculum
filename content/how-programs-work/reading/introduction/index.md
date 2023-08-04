---
title: "Introduction"
date: 2023-07-13T13:40:55-05:00
draft: false
weight: 1
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

   > "It'll take a few moments to get the coordinates from the navicomputer." - Han Solo

## Programs

Given a set of inputs, Han's computer analyzes the data and returns information about safely navigating a hyperspace jump. The computer does this by running a **program**.

At the most basic level, a program is a set of instructions that tell a computer or other machine what to do. These instructions consist of a set of commands, calculations, and manipulations that achieve a specific result. However, the computer cannot solve the problem on its own. Someone---a programmer---had to figure out a series of steps for the computer to follow. Also, the programmer had to write these steps in a way the computer can understand.

## Algorithms

Imagine following a recipe for baking a batch of cookies. After the list of ingredients comes a series of step-by-step instructions for producing the treats. If you want to make something else, like a cake or a roast, you follow a different set of steps using a different set of ingredients.

An **algorithm** is like a recipe. It is a systematic series of steps that, when followed, produce a specific result to help solve a problem. Programmers design algorithms to solve these small steps in a carefully planned way. The results then get combined to produce a final answer or action.

Let's take a look at an example of an algorithm---alphabetizing a list of words:
`apple`, `pear`, `zebra`, `box`, `rutabaga`, `fox`, `banana`, `socks`, `foot`

One possible set of steps for solving the task could be:
1. Arrange the words from ‘A-Z’ based only on the first letter:
   `apple`, `box`, `banana`, `fox`, `foot`, `pear`, `rutabaga`, `socks`, `zebra`

1. If more than one word starts with 'a', rearrange those words based on the second letter. Repeat for the words that start with 'b', then 'c', etc.:
   `apple`, `banana`, `box`, `fox`, `foot`, `pear`, `rutabaga`, `socks`, `zebra`

1. If multiple words start with 'a' and have the same second letter, rearrange those words based on the third letter. Repeat for the 'b' words, then the 'c' words, etc.:
   `apple`, `banana`, `box`, `foot`, `fox`, `pear`, `rutabaga`, `socks`, `zebra`

1. If other repeats exist, continue sorting the list by comparing the 4th, 5th, 6th letters (etc.) until all the words are properly arranged.

This is not the ONLY way to solve the task, but it provides a series of steps that can be used in many different situations to organize different lists of words.

Alphabetizing is a process we can teach a computer to do, and the algorithm will complete the process much more rapidly than a human. However, unlike the alphabet song that many of us still sing in our heads when arranging a list of words, programmers must use a different method to train the computer.


## Checking Your Understanding

{{% notice green  "Question" "rocket" %}} 
 Select ALL of the following that can be solved by using an algorithm:
   1. Answering a math problem.
   1. Sorting numbers in decreasing order.
   1. Making a peanut butter and jelly sandwich.
   1. Assigning guests to tables at a wedding reception.
   1. Creating a grocery list.
   1. Suggesting new music for a playlist.
   1. Making cars self-driving.
<!-- ans: any and all of these. they all have steps and processes for completion  -->
{{% /notice %}}