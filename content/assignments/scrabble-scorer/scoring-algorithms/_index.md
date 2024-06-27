---
title: "Task 2: Add and Organize Scoring Algorithms"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas 
reviewerGitHub: icre8FreeCode 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Your job here is to write two other scoring algorithms for the Scrabble player.

1. `simpleScorer`: Define a function that takes a word as a parameter and
   returns a numerical score. Each letter within the word is worth 1 point.
1. `vowelBonusScorer`: Define a function that takes a word as a parameter and
   returns a score. Each vowel within the word is worth 3 points, and each
   consonant is worth 1 point.

{{% notice blue "Note" "rocket" %}}

   Make each scoring algorithm case *insensitive*, meaning that they
   should all ignore case when assigning points.

{{% /notice %}}

Once you've written these scoring functions, organize all three of the scoring options into an array.
Your program will use the `scoringAlgorithms` array to retrieve information about the 
three scoring algorithms and convey that information to the user. 

1. Finish writing the `scoringAlgorithms` array. It should be populated with three objects, one for each of the three scoring options. 
   Each object should contain three keys: `name`, `description`, and `scorerFunction`.
1. Examine the table for the information to store in `name` and
   `description`. The `scorerFunction` for each object should be the name of
   one of the three scoring algorithms already defined.

   | Name | Description | Score Function |
   |------|-------------|----------------|
   | Simple Score | Each letter is worth 1 point. | A function with a parameter for user input that returns a score. |
   | Bonus Vowels | Vowels are 3 pts, consonants are 1 pt. | A function that returns a score based on the number of vowels and consonants. |
   | Scrabble | The traditional scoring algorithm. | Uses the ``oldScrabbleScorer()`` function to determine the score for a given word. |


1. Finish writing `scorerPrompt()` so that the user can select which scoring algorithm to use when the program scores their word. 
   Use the selected algorithm to determine the score for the word:

   1. If the user enters `0`, have the program output a score using the simple scorer.
   1. If the user enters `1`, use the vowel bonus scoring function.
   1. If the user enters `2`, use the Scrabble scoring option.

   `scorerPrompt()` should return the object the user has selected.

   {{% notice green "Tip" "rocket" %}}

   Your `scoringAlgorithms` structure now holds all of the scoring information required for the program.

   To access a scoring object and its properties, use a combination of bracket notation and dot notation.

   Here is an example:

   ```js
      // Simple scoring
      console.log("algorithm name: ", scoringAlgorithms[0].name);
      console.log("scorerFunction result: ", scoringAlgorithms[0].scorerFunction("JavaScript"));
   ```

   Console Output

   ```console
      algorithm name:  Simple Score
      scorerFunction result:  10
   ```
   {{% /notice %}}

1. Call `scorerPrompt()` inside of `runProgram()` so that the program asks the user for a scoring algorithm after prompting for a word.
   Use the scoring object returned from `scorerPrompt()` to score the user's word and let the user know what score their word receives.

Before moving forward, your running program should behave roughly like this:

```console
   $ node index
   Let's play some Scrabble!

   Enter a word to score: coconut
   Which scoring algorithm would you like to use?

   0 - Simple: One point per character
   1 - Vowel Bonus: Vowels are worth 3 points
   2 - Scrabble: Uses scrabble point system
   Enter 0, 1, or 2: 0
   Score for 'coconut': 7
```
