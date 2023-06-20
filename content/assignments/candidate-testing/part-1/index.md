---
title: "Part 1: Minimum Viable Quiz"
date: 2023-06-20T10:39:25-05:00
draft: false
weight: 2
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

For Part 1, you are going to:  

1. Ask the candidate for their name
1. Create a quiz that asks a single question
1. Check if the candidate answered the question correctly
1. Inform the candidate if they answered the question correctly or not
1. Create a greeting using the candidate's name

The starter code contains functions.  These pieces of code will be covered later in this course.  However, instructions have been provided to help you work with them.
The final page of these instructions will have a little more information about functions if you are curious.  

We have added `TODO` statements in the starter code to guide you with these functions.

For the sake of this assignment, look for the `TODO` statements. Some are outside of a function, and some are within a function.  The location indicates where you should add your code.

## 1.1 `candidateName`

1. Ask for the candidate's name. 
   1. Look for `TODO 1.1a` in the starter code.  
   1. On the line below the TODO statement,  define a variable called `candidateName`.
   1. Declare this variable as an empty string.
1. Look for `TODO 1.1b` inside the `askForName` function.
   1. On the line below the TODO statement (and inside the function), write code that asks the user to enter their name into the program and store the value as `candidateName`.
1. Look for `TODO 1.1c` Underneath it, there is an empty `console.log` statement.  Write a message to the console greeting the user with the name they just provided.

## 1.2 Single Question Quiz

1. Ask the user to answer a single quiz question. Look for `TODO 1.2a`. Below the TODO statement, define variables called `question`, `correctAnswer`, and `candidateAnswer`.

   1. `question` should be initialized to the following string: `"Who was the first American woman in space? "`.

   {{% notice blue "Note" "rocket" %}} 
   Note the trailing space at the end of this string is required.
   {{% /notice %}}

   1. `correctAnswer` should be initialized to `"Sally Ride"`.
   1. `candidateAnswer` will initially be set to the empty string.

1. Find `TODO 1.2b`. Using your question variable, display the question and prompt the candidate for their answer. Store their response in one of the variables you defined just above.

Under `TODO 1.2c`, check the candidate's answer to see if it is correct. Provide basic feedback to the candidate, letting them know if their answer is correct or not.

   {{% notice blue "Note" "rocket" %}} 
   Make sure your small app works properly before moving on to part 2.

   This is also a great time to save, commit, and push up your work.
   {{% /notice %}}


### Troubleshooting Tips

1. Readline-sync not working?
   1. run the following in your terminal inside your project directory:
      `npm i readline-sync`

Ready for [Part 2]({{< relref "../part-2/index.md" >}})
