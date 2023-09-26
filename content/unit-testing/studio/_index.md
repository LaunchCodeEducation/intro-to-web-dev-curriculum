---
title: "Studio: Unit Testing"
date: 2023-09-06T13:40:41-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

LaunchCode's Marketing Team needs your help! To make the website more maintainable, they thought an object called `launchcode` that contains important facts and functions they need would be helpful.
This way if they need to make a change to one of the facts, they just have to change the object in one place as opposed to going through pages of code to make the change in every place.

Here is what they need the `launchcode` object to contain:

1. A key called `organization` with a value of `"nonprofit"`.
1. A key called `executiveDirector` with a value of `"Jeff"`.
1. A key called `percentageCoolEmployees` with a value of `100`.
1. A key called `programsOffered` with a value of `["Web Development", "Data Analysis", "Liftoff"]`.
1. And a method called `launchOutput()`. This method will return a string.

Let's use Test-Driven Development to write this code! Rather than complete the code and *then* test it, TDD flips the process:

1. Write a test first - one that checks the program for a specific outcome.
1. Run the test to make sure it fails.
1. Write a code snippet that passes the test.
1. Repeat steps 1 - 3 for the remaining features of the program.
1. Examine the code and test scripts, and refactor them to increase efficiency.
   Remember the DRY idea (Don't Repeat Yourself).

## Source Code

Open up the `studio` directory in `javascript-projects/unit-testing` and note the files:

1. `index.js` holds the object we want to design.
1. `tests/launchcode.test.js` holds the testing script.

The files are mostly empty. Only a framework has been provided for you. Run `npm install` in the terminal to get everything ready to go.

## Start With the Properties

Let's start our work with the properties we need to add to the object.

### `organization`

1. Inside the `describe` function in `launchcode.test.js`, write a test that will check that the value of `organization` is `"nonprofit"`. Run your test.
1. With your test complete, turn your attention to `index.js` and add the `organization` property to `launchcode`.
1. Run your tests to make sure that everything works as expected.

### `executiveDirector`

1. Write a new test that will check that the value of `executiveDirector` is `"Jeff"`. Run your test.
1. Add the `executiveDirector` property to `launchcode`.
1. Run your tests!

### `percentageCoolEmployees`

1. Write another test that will check that the value of `percentageCoolEmployees`. Run your test.
1. Add `percentageCoolEmployees` to `launchcode`.
1. Run your tests!

### `programsOffered`

1. Write a fourth test that will check the value of `programsOffered`. You should have four `expect` statements within your test. Three of them should check that the array contains the appropriate values and the final one should check that the array is the appropriate size.
   Before moving on, take a moment either individually or with a classmate, to reflect on why you would need these four `expect` statements. Run your test.
1. Add the `programsOffered` property to `launchcode`.
1. Run your tests!

You now have the properties set up for the `launchcode` object. Time to move on to creating the `launchOutput()` method.

## `launchOutput()`

`launchOutput()` needs to meet the following conditions:

1. When passed a number that is ONLY divisible by 2, return `'Launch!'`
1. When passed a number that is ONLY divisible by 3, return `'Code!'`
1. When passed a number that is ONLY divisible by 5, return `'Rocks!'`
1. When passed a number that is divisible by 2 AND 3, return `'LaunchCode!'`
1. When passed a number that is divisible by 3 AND 5, return `'Code Rocks!'`
1. When passed a number that is divisible by 2 AND 5, return
   `'Launch Rocks!'`
1. When passed a number that is divisible by 2, 3, AND 5, return `'LaunchCode
   Rocks!'`
1. When passed a number that is NOT divisible by 2, 3, or 5, return
   `'Rutabagas! That doesn't work.'`

To make sure that you meet all of these conditions, you need to take it one test at a time.

### Write the First Test

In `launchcode.test.js`, complete the `describe` function by adding a
test for condition #1:

> When passed a number that is ONLY divisible by 2, `launchOutput()` returns `'Launch!'`

Run the test. It should fail because there is no code inside `launchOutput()`
yet!

### Write Code to Pass the First Test

In `index.js`, use an `if` statement inside the `launchOutput()`
function to check if the parameter is evenly divisible by 2, and then return an
output. (*Hint: modulus*).

Run the test script again to see if your code passes. If not, modify
`launchOutput()` until it does.

### Write the Next Two Tests

In `launchcode.test.js`, add tests for the conditions:

1. When passed a number that is ONLY divisible by 3, `launchOutput()` returns
   `'Code!'`
1. When passed a number that is ONLY divisible by 5, `launchOutput()` returns
   `'Rocks!'`

Run the tests. The two new ones should fail, but the first
should still pass. Modify the `it` statements as needed if you see a
different result.

### Write Code to Pass the New Tests

Add more code inside `launchOutput()` to check if the parameter is evenly
divisible by 2, 3, or 5, and then return an output based on the result.

Run the test script again to see if your code passes all three tests. If not,
modify `launchOutput()` until it does.

### Hmmm, Tricky

In `launchcode.test.js`, add a test for the condition:

   When passed a number that is divisible by 2 AND 3, `launchOutput()` returns `'LaunchCode!'` (not `'Launch!Code!'`).

Run the tests. Only the new one should fail.

Modify `launchOutput()` until the function passes all four of the tests.

### More Tests and Code Snippets

Continue adding ONE test at a time for the remaining conditions. After you add
EACH new test, run the script to make sure it FAILS, while the previous tests
still pass.

Modify `launchOutput()` until the function passes the new test and all of the
old ones.

Presto! By starting with the *testing* script, you constructed `launchOutput()`
one segment at a time. The result is complete, valid code that has already
been checked for accuracy.

## New Condition

Now that your function passes all 8 tests, let's change one of the conditions.
For the case where a number is divisible by both 2 and 5, instead of returning
`'Launch Rocks!'`, we want the function to return `'Launch Rocks!
(CRASH!!!!)'`.

Modify the testing and function code to deal with this new condition.

## Bonus Missions

### DRYing the Code

Examine `launchOutput()` and the `describe` functions. Notice that there is
quite a bit of repetition in the code.

Try adding arrays, objects, and/or loops to refactor the code into a more
efficient structure.