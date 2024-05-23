---
title: "Task 2: Multiple Questions"
date: 2023-06-20T10:39:25-05:00
draft: false
weight: 3
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: John Woolbright
reviewerGitHub: jwoolbright23
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Now that your small app is working, expand it to deal with multiple questions. This time, you only have one `TODO` item in the starter code. You will need to determine which lines need to be modified.

1. Define `questions` and `correctAnswers` variables as arrays. Use the table below to fill these arrays.

1. Replace your code from `TODO 1.2b` with a loop that programmatically asks each question in the array and stores the user's responses.

1. Replace the basic feedback from `TODO 1.2c` with a template literal that displays each of the candidate's responses in addition to the corresponding correct answers.

| Question      | Answer |
| ----------- | ----------- |
| Who was the first American woman in space?     | "Sally Ride"       |
| True or false: 5 kilometer == 5000 meters?   | "true"        |
| (5 + 3)/2 * 10 = ? | "40"   |
| Given the array `[8, 'Orbit', 'Trajectory', 45]`, what entry is at index 2?   | "Trajectory" |
| What is the minimum crew size for the ISS? | 3   |

{{% notice orange "Warning" "rocket" %}} 
 Keep the questions and correct answers stored in this exact order.
{{% /notice %}}

   {{% notice blue "Note" "rocket" %}} 
   Make sure your loops work properly before moving on to task 3.

   This is also a great time to save, commit, and push up your work.
   {{% /notice %}}

## Testing Task 2

In the terminal run `npm test`.  This will run the autograding tests.  The results will display in the terminal.

   > To pass Task 2, you need to pass tests 7-10.  

You should still pass tests 1-6 from Task 1. 

Move on to [Task 3]({{< relref "../task-3/index.md" >}})