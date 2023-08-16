---
title: "Exercises: Debugging"
date: 2023-08-01T10:26:29-05:00
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

Imagine we are running a space station. Your job is to evaluate the station's code and fix any errors. 
The lives of the crew rest squarely upon your shoulders. 

Your directions from superiors:

1. Launch the shuttle *only if* the fuel, crew and computer all check out OK.
1. If a check fails, print that information to the console and scrub the
   launch.
1. If all checks are successful, print a countdown to launch in the console.

To get started, check out the `exercises` directory in `javascript-projects/errors-and-debugging`.

## Debugging Practice

1. Fix **syntax errors** first. Run the code in `Debugging1stSyntaxError.js` as-is and read the error message. 
   Fix the mistake, and then re-run the code to check it.

   ```js {linenos=table}
   let launchReady = false;
   let fuelLevel = 17000;

   if (fuelLevel >= 20000 {
      console.log('Fuel level cleared.');
      launchReady = true;
   } else {
      console.log('WARNING: Insufficient fuel!');
      launchReady = false;
   }
   ```

   {{% expand "Check your solution" %}}

   Line 4 needs a closing parenthesis:

   `if (fuelLevel >= 20000) {`

   {{% /expand %}}

1. The next block of code in `DebuggingSyntaxErrors2.js` hides two syntax errors. Run the code as-is to
   find the mistakes. 
   
   ```js {linenos=table}
   let launchReady = false;
   let crewStatus = true;
   let computerStatus = 'green';

   if (crewStatus &&& computerStatus === 'green') {
      console.log('Crew & computer cleared.');
      launchReady = true;
   } else {
      console.log('WARNING: Crew or computer not ready!');
      launchReady = false;
   }

   if (launchReady) {
      console.log(("10, 9, 8, 7, 6, 5, 4, 3, 2, 1...");
      console.log("Fed parrot...");
      console.log("Ignition...");
      console.log("Liftoff!");
   } else {
      console.log("Launch scrubbed.");
   }
   ```

   {{% notice green "Tip" "rocket" %}}

   Only one error will
   be flagged at a time. Fix that ONE problem, and then re-run the code to
   check your work. Avoid trying to fix multiple issues at once.

   {{% /notice %}}

1. Fix **runtime errors** next. Open up `DebuggingRuntimeErrors1.js`. Remember to examine the error message for
   clues about what is going wrong. Pay close attention to any line
   numbers mentioned in the message - these will help you locate and repair
   the mistake in the code.

   ```js {linenos=table}
   let launchReady = false;
   let fuelLevel = 17000;

   if (fuellevel >= 20000) {
      console.log('Fuel level cleared.');
      launchReady = true;
   } else {
      console.log('WARNING: Insufficient fuel!');
      launchReady = false;
   }
   ```

   {{% expand "Check your solution" %}}

   `fuellevel` should be fuelLevel on Line 7:

   `if (fuelLevel >= 20000) {`

   {{% /expand %}}

1. *Arrr!*  Did we mention your crew are space pirates? Open up `DebuggingRuntimeErrors2.js`.
   Now find and fix the runtime error in a longer code sample.

   ```js {linenos=table}
   let launchReady = false;
   let fuelLevel = 27000;

   if (fuelLevel >= 20000) {
      console.log('Fuel level cleared.');
      launchReady = true;
   } else {
      console.log('WARNING: Insufficient fuel!');
      launchReady = false;
   }

   if (launchReady) {
      console.log("10, 9, 8...");
      console.log("Fed parrot...");
      console.log("6, 5, 4...");
      console.log("Ignition...");
      consoul.log("3, 2, 1...");
      console.log("Liftoff!");
   } else {
      console.log("Launch scrubbed.");
   }
   ```

1. Solve **logic errors** last. Logic errors do not generate warning
   messages or prevent the code from running, but the program still does
   not work as intended. (Refer to debugging logic errors if you need to
   review).

   1. Open up `DebuggingLogicErrors1.js`. First, run this sample code as-is and examine the output.

      ```js {linenos=table}
      let launchReady = false;
      let fuelLevel = 17000;
      let crewStatus = true;
      let computerStatus = 'green';

      if (fuelLevel >= 20000) {
         console.log('Fuel level cleared.');
         launchReady = true;
      } else {
         console.log('WARNING: Insufficient fuel!');
         launchReady = false;
      }

      if (crewStatus && computerStatus === 'green'){
         console.log('Crew & computer cleared.');
         launchReady = true;
      } else {
         console.log('WARNING: Crew or computer not ready!');
         launchReady = false;
      }

      if (launchReady) {
         console.log('10, 9, 8, 7, 6, 5, 4, 3, 2, 1...');
         console.log('Liftoff!');
      } else {
         console.log('Launch scrubbed.');
      }
      ```

      Should the shuttle have launched? Did it?

      {{% expand "Check your solution" %}}

      The shuttle should not have launched. However, the messages to the console tell a different story. Without any changes, the original code outputs:

      ```console
      WARNING: Insufficient fuel!
      Crew & computer cleared.
      10, 9, 8, 7, 6, 5, 4, 3, 2, 1...
      Liftoff!
      ```

      {{% /expand %}} 

   1. Let's break the code down into smaller chunks. Open up `DebuggingLogicErrors2.js`. Consider the first `if/else` block below. 
      We've commented out some of the variables we're not inspecting right now.
      Add `console.log(launchReady)` after this block, then run the program.

      ```js {linenos=table}
      let launchReady = false;
      let fuelLevel = 17000;
      // let crewStatus = true;
      // let computerStatus = 'green';

      if (fuelLevel >= 20000) {
         console.log('Fuel level cleared.');
         launchReady = true;
      } else {
         console.log('WARNING: Insufficient fuel!');
         launchReady = false;
      }
      ```

      Given the `fuelLevel` value, should `launchReady` be `true` or `false` after the check? Is the program behaving as expected?

   1. Now consider the second `if/else` block. OPen up `DebuggingLogicErrors3.js`. Here again, we comment the variables and blocks that we're not inspecting.
      Add another `console.log(launchReady)` after this block and run the program.

      ```js {linenos=table}
      let launchReady = false;
      // let fuelLevel = 17000;
      let crewStatus = true;
      let computerStatus = 'green';

      // if (fuelLevel >= 20000) {
      //    console.log('Fuel level cleared.');
      //    launchReady = true;
      // } else {
      //    console.log('WARNING: Insufficient fuel!');
      //    launchReady = false;
      // }

      if (crewStatus && computerStatus === 'green'){
         console.log('Crew & computer cleared.');
         launchReady = true;
      } else {
         console.log('WARNING: Crew or computer not ready!');
         launchReady = false;
      }
      ```

      Given `crewStatus` and `computerStatus`, should `launchReady` be `true` or `false` after this check? 
      
      Is the program behaving as expected?

      {{% expand "Check your solution" %}} 

      With their initial values set to `true` and `'green'`, line 14 evaluates to `true` and `launchReady` is set to `true`. If it's value on dependent on the value of these variables only (`crewStatus` and `computerStatus`), then `launchReady` should be `true` after this check.

      {{% /expand %}}

   1. Now consider both `if/else` blocks together (keeping the added `console.log` lines). Run the code in `DebuggingLogicErrors4.js` and examine the output.

      ```js {linenos=table}
      let launchReady = false;
      let fuelLevel = 17000;
      let crewStatus = true;
      let computerStatus = 'green';

      if (fuelLevel >= 20000) {
         console.log('Fuel level cleared.');
         launchReady = true;
      } else {
         console.log('WARNING: Insufficient fuel!');
         launchReady = false;
      }
      console.log(launchReady);

      if (crewStatus && computerStatus === 'green'){
         console.log('Crew & computer cleared.');
         launchReady = true;
      } else {
         console.log('WARNING: Crew or computer not ready!');
         launchReady = false;
      }
      console.log(launchReady);
      ```

      Given the values for `fuelLevel`, `crewStatus` and `computerStatus`, should `launchReady` be `true` or `false`? Is the program behaving as expected?

   1. Ahoy, Houston! We spied a problem! The value of `launchReady` assigned
      in the first `if/else` block got changed in the second `if/else`
      block. Dangerous waters, Matey. Open up `DebuggingLogicErrors5.js` to address this error.
      
      The issue is with the `launchReady` value being assigned and reassigned based on different checks.
      One way to fix the logic error is to use two different variables to store the
      results of checking the fuel readiness (lines 6-13) and checking the crew and computer readiness (lines 15-22). 
      
      Update your code to do this. Verify that your change works
      by updating the `console.log` statements.

   {{% expand "Check your solution" %}}
   ```js {linenos=table}
   let launchReady = false;
   let crewReady = false;
   let fuelLevel = 17000;
   let crewStatus = true;
   let computerStatus = 'green';

   if (fuelLevel >= 20000) {
      console.log('Fuel level cleared.');
      launchReady = true;
   } else {
      console.log('WARNING: Insufficient fuel!');
      launchReady = false;
   }
   console.log("launchReady = ", launchReady);

   if (crewStatus && computerStatus === 'green'){
      console.log('Crew & computer cleared.');
      crewReady = true;
   } else {
      console.log('WARNING: Crew or computer not ready!');
      crewReady = false;
   }
   console.log("crewReady = ", crewReady);
   ```
   {{% /expand %}}

   1. Almost done, so wipe the sweat off your brow! Add a final `if/else` block
      to print a countdown and "Liftoff!" if all the checks pass, or print "Launch
      scrubbed" if any check fails.

      Blimey! That's some good work. 
