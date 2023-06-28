---
title: "Assignment 2: Scrabble Scorer"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

For your second assignment, we'll ask you to modify and improve our Scrabble Scorer program. 
Did you think you were going to work on Mars Rover code already? That will come next!

We want you to update our program that asks a user for a word 
and outputs a score. Your final version will have three scoring algorithms and 
allow a user to interactively choose which algorithm to use. We've provided some starter code that
includes the official Scrabble scoring point system and we'd like you to make 
some modifications to improve it.

Let's roll.

## Requirements

{{% notice blue "Note" "rocket" %}}

   The requirements below are what your assignment should look like when it's 
   time to submit. Rome wasn't built in a day and neither was Scrabble.

   This assignment is broken down so you can complete small pieces as you go.
   You need to move sequentially starting with Part A below. You'll have a much more 
   enjoyable time writing this program if you read this entire page before even opening your code.

{{% /notice %}}

1. Write an `initialPrompt()` function that asks a user to input a word.
1. Have the program return a score for the word using `oldScrabbleScorer()`.
1. Add additional scoring algorithms and store them in the `scoringAlgorithms` array.
1. Create a `transform()` function that takes in the `oldPointStructure`
   object and returns a `newPointStructure` object.
1. Use the `runProgram()` function to serve as the starting point for your
   program.

## Starter Code

Fork and clone the [starter code repo](https://github.com/LaunchCodeEducation/Scrabble-Scorer-Autograded).

You only need to pay attention to one file here, `scrabble-scorer.js`. Within this JavaScript
file is still some more starter code that you don't need to touch. We'll point out what you 
should be modifying here to write your Scrabble Scorer program.

To run the starter code as is, take the following steps:

1. Open the terminal in Visual Studio Code.
1. Run the command, `npm install`.
1. Once that is complete, run the command, `node index`. You'll see a message printed to the console:

```console
   $ node index
   Let's play some Scrabble!
```

{{% notice green "Tip" "rocket" %}}

   If you don't see this message printed and have exhausted your troubleshooting skills, 
   reach out to your classmates or course staff ASAP so you can get started with the real coding.

{{% /notice %}}

Time to code!

## Your Tasks

{{% children %}}



