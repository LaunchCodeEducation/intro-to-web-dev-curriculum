# Exercises: Modules

Practice makes better. You will create a project that accomplishes the
following:

a.  Steps through a list of Yes/No questions.
b.  Calls functions based on the user\'s responses.

Rather than coding all of the functions from scratch, you are going to
use existing modules to help assemble your project.

Open [this link](https://repl.it/@launchcode/ModuleExercises01) and fork
the starter code, then complete the following:

## Export Finished Modules

Lucky you! Some of your teammates have already coded the necessary
functions in the `averages.js` and `display.js` files.

1.  In `averages.js`, add code to export all of the functions within an
    object.
2.  In `display.js`, add code to export ONLY `printAll` as a function.

`Check your solution <modules-solutions1>`{.interpreted-text role="ref"}

## Code & Export New Module

`randomSelect.js` requires your attention.

1.  Add code to complete the `randomFromArray` function. It should take
    an array as an argument and then return a
    `randomly selected element <random-array-item>`{.interpreted-text
    role="ref"} from that array.
2.  Do not forget to export the `randomFromArray` function so you can
    use it in your project.

`Check your solution <modules-solutions2>`{.interpreted-text role="ref"}

## Import Required Modules

The project code is in `index.js`. Start by importing the required
modules:

1.  Assign `readline-sync` to the `input` variable.
2.  Assign the functions from `averages.js` to the `averages` variable.
3.  Assign the `printAll` function from `display.js` to the `printAll`
    variable.
4.  Assign the function from `randomSelect.js` to the `randomSelect`
    variable.

`Check your solution <modules-solutions3>`{.interpreted-text role="ref"}

## Finish the Project

Now complete the project code. (Note - The line references assume that
you added no blank lines during your work in the previous section. If
you did, no worries. The comments in `index.js` will still show you
where to add code).

1.  Line 21 - Call `printAll` to display all of the tests and student
    scores. Be sure to pass in the correct arguments.
2.  Line 24 - Using dot notation, call `averageForTest` to print the
    class average for each test. Use `j` and `scores` as arguments.
3.  Line 29 - Call `averageForStudent` (with the proper arguments) to
    print each astronaut\'s average score.
4.  Line 33 - Call `randomSelect` to pick the next spacewalker from the
    `astronauts` array.

`Check your solution <modules-solutions4>`{.interpreted-text role="ref"}

## Sanity check!

Properly done, your output should look something like:

    Would you like to display all scores? Y/N: y
    Name        Math      Fitness   Coding    Nav       Communication
    Fox         95        86        83        81        76
    Turtle      79        71        79        87        72
    Cat         94        87        87        83        82
    Hippo       99        77        91        79        80
    Dog         96        95        99        82        70

    Would you like to average the scores for each test? Y/N: y
    Math test average = 92.6%.
    Fitness test average = 83.2%.
    Coding test average = 87.8%.
    Nav test average = 82.4%.
    Communication test average = 76%.

    Would you like to average the scores for each astronaut? Y/N: y
    Fox's test average = 84.2%.
    Turtle's test average = 77.6%.
    Cat's test average = 86.6%.
    Hippo's test average = 85.2%.
    Dog's test average = 88.4%.

    Would you like to select the next spacewalker? Y/N: y
    Turtle is the next spacewalker.
