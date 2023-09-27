---
title: "Exercises: Unit Testing"
date: 2023-09-06T13:40:41-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In many of your previous coding tasks, you had to verify that your code
worked before moving to the next step. This often required you to add
`console.log()` statements to your code to check the value stored in a variable
or returned from a function. This approach finds and fixes syntax, reference,
or logic errors AFTER you write your code.

In this chapter, you learned how to use unit testing to solve coding errors.
Even better, you learned how to PREVENT mistakes by writing test cases before
completing the code. The exercises below offer practice with using tests to
find bugs, and the studio asks you to implement TDD.

For the exercises, open `javascript-projects/unit-testing/exercises` to find the files you will need to get started.

## Automatic Testing to Find Errors

Let's begin with the following code in `checkFive.js`:

```js {linenos=table} 
   function checkFive(num){
      let result = '';
      if (num < 5){
         result = num + " is less than 5.";
      } else if (num === 5){
         result = num + " is equal to 5.";
      } else {
         result = num + " is greater than 5.";
      }

      return result;
   }
```

The function checks to see if a number is greater than, less than, or equal to
5. We do not really need a function to do this, but it provides good practice
for writing test cases.

Note that the `exercises` directory also contains a `tests` directory for us.

1. We need to add a few lines to `checkFive.js` and `checkFive.test.js` to
   get them to talk to each other.

   1. `checkFive.test.js` needs to access `checkFive.js`. Add a `require` statement
      to accomplish this.

   1. Make the `checkFive` function available to the spec file, by using
      `module.exports`.

   {{% expand "Check your solution" %}}
   
   `checkFive.test.js`:

   ```js
   const test = require('../checkFive.js');
   ```

   {{% /expand %}}

1. Set up your first test for the `checkFive` function. In the
   `checkFive.test.js` file, add a `describe` function with one `test`
   clause:

   ```js {linenos=table}
      const checkFive = require('../checkFive.js');

      describe("checkFive", function(){

         test("Descriptive feedback...", function() {
            //code here...
         });

      });
   ```

1. Now write a test to see if `checkFive` produces the correct output when
   passed a number *less than 5*.

   1. First, replace `Descriptive feedback...` with a DETAILED message. This
      is the text that the user will see if the test *fails*. Do NOT skimp on
      this. Refer back to Specifications and Expectations
      section to review best practices.

   1. Define the variable `output`, and initialize it by passing a value of
      `2` to `checkFive`.

      ```js {linenos=table}
         const checkFive = require('../checkFive.js');

         describe("checkFive", function(){

            test("Descriptive feedback...", function(){
               let output = checkFive(2);
            });

         });
      ```

   1. Now use the `expect` function to check the result:

      ```js {linenos=table}
         const checkFive = require('../checkFive.js');

         describe("checkFive", function(){

            test("Descriptive feedback...", function(){
               let output = checkFive(2);
               expect(output).toEqual("2 is less than 5.");
            });

         });
      ```

   1. Run the test script and examine the results. The test should pass.

   1. Now change line 3 in `checkFive.js` to `if (num > 5)` and rerun
      the test. 

   1. Change line 3 back.

   {{% notice blue "Note" "rocket" %}}
   We do NOT need to check every possible value that is less than 5. Testing a single
   example is sufficient to check that part of the function.
   {{% /notice%}}

   {{% expand "Check your solution" %}}

   `checkFive.test.js` after writing a declarative test name:

   ```js
      test("returns 'num is less than 5' when num < 5.", function() {
      // test code //
   });
   ```

   `checkFive.test.js` uses `expect`:

   ```js
   expect(output).toBe("2 is less than 5.");
   ```

   Change `checkFive.js` to see the test fail:

   ```js
   if (num > 5) {
      // sourcecode //
   }
   ```

   {{% /expand %}}

1. Add two more `test` clauses inside `describe`---one to test what happens
   when `checkFive` is passed a value greater than 5, and the other to test
   when the value equals 5.

## Try One on Your Own

Time for Rock, Paper, Scissors! The function in `RPS.js` takes the choices
(`'rock'`, `'paper'`, or `'scissors'`) of two players as its parameters.
It then decides which player won the match and returns a string.

```js {linenos=table}
   function whoWon(player1,player2){

      if (player1 === player2){
         return 'TIE!';
      }

      if (player1 === 'rock' && player2 === 'paper'){
         return 'Player 2 wins!';
      }

      if (player1 === 'paper' && player2 === 'scissors'){
         return 'Player 2 wins!';
      }

      if (player1 === 'scissors' && player2 === 'rock '){
         return 'Player 2 wins!';
      }

      return 'Player 1 wins!';
   }
```

1. Set up the `RPS.js` and `RPS.spec.js` files to talk to each other.

   {{% expand "Check your solution" %}}

   RPS.js:

   ```js
   module.exports = {
         whoWon: whoWon
   };
   ```

   RPS.spec.js:

   ```js
   const test = require('../RPS.js');
   ```

   {{% /expand %}}

1. Write a test in `RPS.test.js` to check if `whoWon` behaves correctly
   when the players tie (both choose the same option). Click "Run" and examine
   the output. SPOILER ALERT: The code for checking ties is correct in
   `whoWon`, so the test should pass. If it does not, modify your `test`
   statement.

1. Write tests (one at a time) for each of the remaining cases. Run the tests
   after each addition, and modify the code as needed. There is one mistake in
   `whoWon`. You might spot it on your own, but try to use automated
   testing to identify and fix it.

   {{% expand "Check your solution" %}}

   Here are two sample tests:

   ```js
   test("returns 'Player 2 wins!' if P1 = rock & P2 = paper", function(){
      let output = test.whoWon('rock','paper');
      expect(output).toBe("Player 2 wins!");
   });

   test("returns 'Player 2 wins!' if P1 = paper & P2 = scissors", function(){
      let output = test.whoWon('paper','scissors');
      expect(output).toBe("Player 2 wins!");
   });
   ```

   {{% /expand %}}

## Bonus Mission

What if something OTHER than `'rock'`, `'paper'`, or `'scissors'` is
passed into the `whoWon` function? Modify the code to deal with the
possibility.

Don't forget to add another `test` clause in `RPS.test.js` to test for this
case.