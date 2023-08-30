---
title: "Exercises: Loops"
date: 2023-08-28T09:21:11-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

> Practice makes better. Repetition is a good thing. Repetition is a good thing. Repetition is a good thing. Repetition is a good thing.

WAIT!!!  Why type "Repetition is a good thing," four times when we can code
a better result?  How about printing the phrase 100 times instead?

```js {linenos = true}
for (let i = 0; i < 100; i++){
   console.log("Repetition is a good thing.");
}
```

Loops simplify repetitive tasks!

## `for` Practice

Open up `for-Loop-Exercises.js` in `loops/exercises` in `javascript-projects`. This is the file you will use to test your skills with `for` loops.

1. Construct `for` loops that accomplish the following tasks:

   1. Print the numbers 0 - 20, one number per line.
   1. Print only the ODD values from 3 - 29, one number per line.
   1. Print the EVEN numbers 12 down to -14 in descending order, one number
      per line.
   1. Print the numbers 50 down to 20 in descending order, but only
      if the numbers are multiples of 3.

   {{% expand "Check your solution" %}}
   1. Print the numbers 0 - 20, one number per line.
   ```js
   for (let i = 0; i <= 20; i++) {
      console.log(i);
   }
   ```
   3. Print the EVEN numbers 12 down to -14 in descending order, one number per line.
   ```js
   for (let i = 12; i >= -14; i-=2) {
      console.log(i);
   }
   ```
   {{% /expand %}}

1. Initialize two variables to hold the string `'LaunchCode'` and the array
   `[1, 5, 'LC101', 'blue', 42]`, then construct `for` loops to accomplish
   the following tasks:

   1. Print each element of the array to a new line.
   1. Print each character of the string---in reverse order---to a new line.

   {{% expand "Check your solution" %}}
   1. Print each element of the array to a new line.
   ```js
   for (let i = 0; i < arr.length; i++) {
      console.log(arr[i]);
   }
   ```
   {{% /expand %}}

1. Construct a `for` loop that sorts the array
   `[2, 3, 13, 18, -5, 38, -10, 11, 0, 104]` into two new arrays:

   1. Define an empty `evens` array to hold the even numbers and an `odds`
      array for the odd numbers.
   1. In the loop, determine if each number is even or odd, then put that
      number into `evens` or `odds`, as appropriate.
   1. Print the arrays to confirm the results. Print `evens` first. Example:
      `console.log(evens);`

   {{% expand "Check your solution" %}}
   1. Define an empty evens array to hold the even numbers and an odds array for the odd numbers.
   ```js
   let otherArr = [2, 3, 13, 18, -5, 38, -10, 11, 0, 104];
   let evens = [], odds = [];
   ```
   3. Print the arrays to confirm the results. Print evens first. Example: console.log(evens);
   ```js
   console.log(evens);
   console.log(odds);
   ```
   {{% /expand %}}

## `while` Practice

To practice with `while` loops, open up `while-Loop-Exercises.js` in `loops/exercises` in `javascript-projects`.

Define three variables for the LaunchCode shuttle---one for the starting
fuel level, another for the number of astronauts aboard, and the third for
the altitude the shuttle reaches.

4. Construct `while` loops to do the following:

   1. Prompt the user to enter the starting fuel level. The loop should continue until
      the user enters a positive value greater than 5000 but less than 30000.
   1. Use a second loop to query the user for the number of astronauts
      (up to a maximum of 7). Validate the entry by having the loop continue
      until the user enters an integer from 1 - 7.
   1. Use a final loop to monitor the fuel status and the altitude of the
      shuttle. Each iteration, decrease the fuel level by 100 units for each
      astronaut aboard. Also, increase the altitude by 50 kilometers. (Hint:
      The loop should end when there is not enough fuel to boost the crew
      another 50 km, so the fuel level might not reach 0).

   {{% expand "Check your solution" %}}
   1. Prompt the user to enter the starting fuel level. The loop should continue until the user enters a positive value greater than 5000 but less than 30000.
   ```js
   const input = require('readline-sync');
   let fuelLevel = 0, numAstronauts = 0, altitude = 0;

   while (fuelLevel <= 5000 || fuelLevel > 30000 || isNaN(fuelLevel)) {
      fuelLevel = input.question("Enter the starting fuel level: ");
   }
   ```
   3. Use a final loop to monitor the fuel status and the altitude of the shuttle. Each iteration, decrease the fuel level by 100 units for each astronaut aboard. Also, increase the altitude by 50 kilometers. (Hint: The loop should end when there is not enough fuel to boost the crew another 50 km, so the fuel level might not reach 0).
   ```js
   while (fuelLevel-100*numAstronauts >= 0) {
   altitude += 50;
   fuelLevel -= 100*numAstronauts;
   }
   ```
   {{% /expand %}}

5. After all the loops complete, output the result with the phrase, `The shuttle
   gained an altitude of ___ km.`

   1. If the altitude is 2000 km or higher, add "Orbit achieved!"
   1. Otherwise add, "Failed to reach orbit."

   {{% expand "Check your solution" %}}
   1. If the altitude is 2000 km or higher, add "Orbit achieved!"
   ```js
   let output = `The shuttle gained an altitude of ${altitude} km.`;

   if (altitude >= 2000) {
   output += " Orbit achieved!";
   }
   ```
   {{% /expand %}}