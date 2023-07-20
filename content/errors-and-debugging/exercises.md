# Exercises: Debugging {#exercises-errors-and-debugging}

Imagine we are running a space station. Your job is to evaluate the
station\'s code and fix any errors. The lives of the crew rest squarely
upon your shoulders.

Your directions from superiors:

1.  Launch the shuttle *only if* the fuel, crew and computer all check
    out OK.
2.  If a check fails, print that information to the console and scrub
    the launch.
3.  If all checks are successful, print a countdown to launch in the
    console.

## Debugging Practice

A.  Fix **syntax errors** first. Run the following code as-is and read
    the error message. Fix the mistake, and then re-run the code to
    check it.

    ``` {.js linenos=""}
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

    [Fix it at repl.it](https://repl.it/@launchcode/Debug1stSyntaxError)

    `Check your solution <errors-and-debugging-exercise-solutionsA>`{.interpreted-text
    role="ref"}.

B.  The next block of code hides two syntax errors. Run the code as-is
    to find the mistakes.

    ``` {.js linenos=""}
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

    ::: admonition
    Tip

    Only one error will be flagged at a time. Fix that ONE problem, and
    then re-run the code to check your work. Avoid trying to fix
    multiple issues at once.
    :::

    [Fix it at repl.it](https://repl.it/@launchcode/DebugSyntaxErrors2)

C.  Fix **runtime errors** next. Remember to examine the error message
    for clues about what is going wrong. Pay close attention to any line
    numbers mentioned in the message - these will help you locate and
    repair the mistake in the code.

    ``` {.js linenos=""}
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

    [Fix it at repl.it](https://repl.it/@launchcode/DebugRuntimeErrors1)

    `Check your solution <errors-and-debugging-exercise-solutionsC>`{.interpreted-text
    role="ref"}.

D.  *Arrr!* Did we mention your crew are space pirates? Now find and fix
    the runtime error in a longer code sample.

    ``` {.js linenos=""}
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

    [Fix it at repl.it](https://repl.it/@launchcode/DebugRuntimeErrors2)

E.  Solve **logic errors** last. Logic errors do not generate warning
    messages or prevent the code from running, but the program still
    does not work as intended. (Refer to
    `debugging logic errors <debugging-logic-errors>`{.interpreted-text
    role="ref"} if ye need to review).

    1.  First, run this sample code as-is and examine the output.

        ``` {.js linenos=""}
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

        [Run it at
        repl.it](https://repl.it/@launchcode/DebugLogicErrors1)

        Should the shuttle have launched? Did it?

        `Check your answer <errors-and-debugging-exercise-solutionsEa>`{.interpreted-text
        role="ref"}.

    2.  Let\'s break the code down into smaller chunks. Consider the
        first `if/else` block below. We\'ve commented out some of the
        variables we\'re not inspecting right now. Add
        `console.log(launchReady)` after this block, then run the
        program.

        ``` {.js linenos=""}
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

        [Run it at
        repl.it](https://repl.it/@launchcode/DebugLogicErrors2)

        Given the `fuelLevel` value, should `launchReady` be `true` or
        `false` after the check? Is the program behaving as expected?

    3.  Now consider the second `if/else` block. Here again, we comment
        the variables and blocks that we\'re not inspecting. Add another
        `console.log(launchReady)` after this block and run the program.

        ``` {.js linenos=""}
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

        [Run it at
        repl.it](https://repl.it/@launchcode/DebugLogicErrors3)

        Given `crewStatus` and `computerStatus`, should `launchReady` be
        `true` or `false` after this check?

        `Check your answer <errors-and-debugging-exercise-solutionsEc>`{.interpreted-text
        role="ref"}.

    4.  Now consider both `if/else` blocks together (keeping the added
        `console.log` lines). Run the code and examine the output.

        ``` {.js linenos=""}
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

        [Run it at
        repl.it](https://repl.it/@launchcode/DebugLogicErrors4)

        Given the values for `fuelLevel`, `crewStatus` and
        `computerStatus`, should `launchReady` be `true` or `false`? Is
        the program behaving as expected?

    5.  Ahoy, Houston! We spied a problem! The value of `launchReady`
        assigned in the first `if/else` block got changed in the second
        `if/else` block. Dangerous waters, Matey.

        The issue is with the `launchReady` value being assigned and
        reassigned based on different checks. One way to fix the logic
        error is to use two different variables to store the results of
        checking the fuel readiness (lines 6-13) and checking the crew
        and computer readiness (lines 15-22).

        Update your code to do this. Verify that your change works by
        updating the `console.log` statements.

        [Fix it at
        repl.it](https://repl.it/@launchcode/DebugLogicErrors5)

        `Check your solution <errors-and-debugging-exercise-solutionsEe>`{.interpreted-text
        role="ref"}.

    6.  Almost done, so wipe the sweat off your brow! Add a final
        `if/else` block to print a countdown and \"Liftoff!\" if all the
        checks pass, or print \"Launch scrubbed\" if any check fails.

        Blimey! That\'s some good work.
