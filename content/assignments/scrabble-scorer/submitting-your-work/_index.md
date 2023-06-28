---
title: "Submitting Your Work"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 5
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Before you submit your work, you should test out your code.

## Test Words

First run some test words with your program. Here are some words you can use to test your code:

1. `JavaScript` = 24 points using Scrabble, 10 using Simple Score, and 16
   using Bonus Vowels.
1. `Scrabble` = 14 points using Scrabble, 8 using Simple Score, and 12 using
   Bonus Vowels.
1. `Zox` = 19 points using Scrabble, 3 using Simple Score, and 5 using Bonus
   Vowels.

### Example Output

Review the code for each test word to see that it works as expected. Here is an example of the output you may see.

```console
   $ node index
   Let's play some Scrabble!

   Enter a word to score: rum
   Which scoring algorithm would you like to use?

   0 - Simple: One point per character
   1 - Vowel Bonus: Vowels are worth 3 points
   2 - Scrabble: Uses scrabble point system
   Enter 0, 1, or 2: 1
   Score for 'june': 8
```

## Autograding Tests

Your starter code came with a suite of tests your TA can use to verify certain behaviors in your code. These tests can be found in the folder named `test`. To see how your code will do with these tests, you can run the command `npm test` in the terminal. If you see a test failed and you are not quite sure why, we encourage you to reach out to course staff for assistance.

## Submitting Your Work

<!-- TODO: Add link to Assignment 0 -->

Follow the submission instructions in Assignment 0 to submit your work. Remember to copy the link to your repo and paste it in the submission box on Canvas so your TA knows you are ready to have your work graded.

## Bonus Missions

1. Currently, the prompts accept ANY input values. The user could enter
   something *other* than 0, 1, or 2 when selecting the scoring algorithm, and
   they could enter numbers or symbols when asked for a word. Modify your code
   to reject invalid inputs and then re-prompt the user for the correct
   information.
1. Score words spelled with blank tiles by adding `' '` to the
   `newPointStructure` object. The point value for a blank tile is `0`.
