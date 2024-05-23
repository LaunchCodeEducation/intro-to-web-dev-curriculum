---
title: "Project Introduction"
date: 2023-06-20T10:39:25-05:00
draft: false
weight: 1
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: John Woolbright
reviewerGitHub: jwoolbright23
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Getting Started

Welcome to your first graded assignment.  We would like you to create a short quiz console application.

Fork and clone the [starter code repo](https://github.com/LaunchCodeEducation/Candidate-Testing-Autograded/tree/main).

1. Open a terminal and `cd` into the project file.
   1. You will see `candidate-testing.js` and other files if you run `ls`
1. Run `npm install` to bring in all of the packages you need to run the application

You should be ready to code your application.  Good luck! 


## Requirements

The requirements below are what your END assignment will look like. 

1. Ask the candidate (user) to enter their name
1. Use a loop to ask five questions, one at a time, to the candidate
1. Collect the candidate's answers
1. Check those answers for accuracy (case insensitive equality check)
1. Calculate the candidate's overall percentage
1. Determine if the candidate did well enough to enter our program (need >= 80% to pass)
1. Display the results.

This assignment is broken down so you can complete small pieces as you go. You need to move sequentially starting at Task 1. Please read the WHOLE assignment page before starting.

## Take It Step by Step
When starting any project, it's best to approach it as a series of smaller, testable tasks. The goal is to get simple tasks working first and then expand the code in a systematic way. The following is NOT the only way to complete this assignment, but it provides a framework for thinking through the project.

To help you with this large assignment, we have broken it into 3 tasks.

**Task 1: Minimum Viable Quiz**

You will create a single question quiz.  This will let you see the overall project in a smaller scale.
   1. You will create 1 question with 1 correct answer.  
   1. You will collect 1 answer from the user.
   1. You will compare the correct answer with the user's answer and let the user know if they got the question right.

You will run the autograding tests before moving onto Task 2.  You need to pass Tests 1-6.

**Task 2: Multiple Questions**

You will increase the number of questions and answers to 5.  

You will need to update your single question quiz to a 5 question quiz. 
This will also mean, you will also have 5 correct answers and you will collect 5 user answers.

You will run the autograding tests before moving onto Task 3.  You need to pass Tests 7-10.

**Task 3: Grade the Quiz**

In this section, you will score the candidate's quiz results and let them know if they passed or failed.

You will run the autograding tests before moving onto Task 3.  You need to pass Tests 11-17 for this section.  You should pass all 17 tests to complete the assignment.

## Example Output

Once all three tasks have been completed, the results output should include the candidate's name, the candidate's responses, the correct answers, the final percentage, and if the candidate passed the quiz.

```bash
Candidate Name: Can Twin
1) Who was the first American woman in space?
Your Answer: sally ride
Correct Answer: Sally Ride

2) True or false: 5000 meters = 5 kilometers.
Your Answer: false
Correct Answer: true

3) (5 + 3)/2 * 10 = ?
Your Answer: 45
Correct Answer: 40

4) Given the array [8, "Orbit", "Trajectory", 45], what entry is at index 2?
Your Answer: trajectory
Correct Answer: Trajectory

5) What is the minimum crew size for the ISS?
Your Answer: 10
Correct Answer: 3

>>> Overall Grade: 40% (2 of 5 responses correct) <<<
>>> Status: FAILED <<<
```

{{% notice blue "Note" "rocket" %}} 
 The output will vary slightly based on the candidate's answers to each question.
{{% /notice %}}

Let's get started on [Task 1]({{< relref "../task-1/index.md" >}})


