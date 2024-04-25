---
title: "Task 4: Transform the Object"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright
reviewerGitHub: jwoolbright23 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

1. Write the rest of the `transform()` function. It will need to take an object 
   as a parameter - specifically the `oldPointStructure` object. Calling
   `transform(oldPointStructure)` will return an object with *lowercase*
   letters as keys. The value for each key will be the points assigned to that
   letter.

   {{% notice green "Tip" "rocket" %}}
   1. Recall that `for...in` loops iterate over the keys within an object.
   1. If you need a reminder of how to assign new key/value pairs, review the
      relevant section in the
      `Objects and Math` chapter.
   1. To access the letter arrays within `oldPointStructure`, use bracket
      notation (`oldPointStructure[key]`).
   1. To access a particular element within a letter array, add a second set of
      brackets (`oldPointStructure[key][index]`), or assign the array to a
      variable and use `variableName[index]`.

      ```js {linenos=table}
      console.log("Letters with score '4':", oldPointStructure[4]);
      console.log("3rd letter within the key '4' array:", oldPointStructure[4][2]);

      let letters = oldPointStructure[8];
      console.log("Letters with score '8':", letters);
      console.log("2nd letter within the key '8' array:", letters[1]);
      ```

      **Console Output**

      ```console
      Letters with score '4': [ 'F', 'H', 'V', 'W', 'Y' ]
      3rd letter within the key '4' array: V

      Letters with score '8': [ 'J', 'X' ]
      2nd letter within the key '8' array: X
      ```
      {{% /notice %}}


1. Locate the `newPointStructure` object in the starter code and set it equal to
   `transform(oldPointStructure)`.


   {{% notice orange "Warning" "rocket" %}}

   Hard-coding the `newPointStructure` object literal like this:

   ```js
   let newPointStructure = 
   {
      a:1,
      b: 1,
      c: 1,
      etc ...
   }
   ```

   won't pass. And you'll lose an opportunity to practice this skill.
   {{% /notice %}}

1. Once you've defined `newPointStructure`, use it to finish writing the `scrabbleScorer()` function and then replace 
   the `oldScrabbleScorer()` function in `scoringAlgorithms` with this new function.

   {{% notice green "Tip" "rocket" %}}

   `oldScrabbleScorer()` uses `oldPointStructure` and returns a score for each letter in a word. You'll want to write
   `scrabbleScorer()` to use `newPointStructure` and return a cumulative score for the whole word entered.
   
   {{% /notice %}}