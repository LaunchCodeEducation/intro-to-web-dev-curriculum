# Exercises: TypeScript

## Part 0 - Get the Starter Code {#TS-repo}

1.  Login to your GitHub account.

2.  Fork the [typescript-lc101-projects
    repository](https://github.com/LaunchCodeEducation/typescript-lc101-projects).

3.  Use the terminal to clone your fork from GitHub. If you need a
    reminder for how to do this, refer to the
    `Git studio <clone-from-git>`{.interpreted-text role="ref"}.

4.  Use the terminal to navigate into the `typescript-lc101-projects`
    folder, then into the `exercises` subfolder.

    ``` bash
    $ ls
       typescript-lc101-projects
    $ cd typescript-lc101-projects
    $ ls
       exercises       studio
    $ cd exercises
    $ ls
       SpaceLocation.ts     parts1-5.ts    tsconfig.json
    ```

## Part 1 - Declare Variables With Type

Run VSCode and open the `typescript-lc101-projects` folder. From the
file tree, select the `parts1-5.ts` file.

<figure>
<img src="./figures/TS-exercises-file-tree.png"
alt="./figures/TS-exercises-file-tree.png" />
<figcaption>VSCode file tree</figcaption>
</figure>

In the space indicated, declare and assign a variable for each of the
following:

  Variable Name         Type     Value
  --------------------- -------- -------------------
  spacecraftName        string   `'Determination'`
  speedMph              number   17500
  kilometersToMars      number   225000000
  kilometersToTheMoon   number   384400
  milesPerKilometer     number   0.621

`Check your solution <typescript-exercise-solutions1>`{.interpreted-text
role="ref"}

## Part 2 - Print Days to Mars

In the *same* file you opened in Part 1, do the following.

1.  Declare and assign these variables.
    a.  Remember: variable declarations in TypeScript include the type!
    b.  `milesToMars` is a number with the value of
        `kilometersToMars * milesPerKilometer`.
    c.  `hoursToMars` is a number with the value of
        `milesToMars / speedMph`.
    d.  `daysToMars` is a number with the value of `hoursToMars / 24`.
2.  Write a `console.log` statement that prints out the days to Mars.
    a.  Use template literal syntax and the variables
        `${spacecraftName}` and `${daysToMars}`.
3.  Use the terminal in VSCode to compile your `.ts` file, then use the
    command `node parts1-5.js` to run the JavaScript file created during
    the build process.

**Terminal**

    $ tsc parts1-5.ts
    $ node parts1-5.js
       Determination would take 332.67857142857144 days to get to Mars.

`Check your solution <typescript-exercise-solutions2>`{.interpreted-text
role="ref"}

## Part 3 - Create a Function

1.  In the space indicated, define a function that calculates the days
    it would take to travel to a location.
    a.  Function name `getDaysToLocation`
    b.  Parameter
        -   `kilometersAway` must be a number.
    c.  Returns the number of days to a location.
        -   Use the same calculations as in Part 2.1.
        -   Inside the function, make the variable names generic. Use
            `milesAway` and `hoursToLocation` instead of `milesToMars`
            and `hoursToMars`.
        -   The function should declare that it returns a `number`.
2.  Print out the days to Mars.
    a.  Move the output statement from part 2 below your new function.
    b.  Refactor the template literal to use
        `${getDaysToLocation(kilometersToMars)}` and
        `${spacecraftName}`.
3.  Print out the days to the Moon.
    a.  Add another output statement and template literal using
        `${getDaysToLocation(kilometersToTheMoon)}` and
        `${spacecraftName}`.
4.  Use the terminal in VSCode to recompile your `.ts` file, then run
    the `parts1-5.js` file again.

**Terminal**

    $ tsc parts1-5.ts
    $ node parts1-5.js
       Determination would take 332.67857142857144 days to get to Mars.
       Determination would take 0.5683628571428571 days to get to the Moon.

`Check your solution <typescript-exercise-solutions3>`{.interpreted-text
role="ref"}

## Part 4 - Create a Spacecraft Class

Organize `getDaysToLocation` and the variables for name, speed, and
miles per kilometer by moving them into a *class*.

1.  Define a class named `Spacecraft`.

    a.  Properties
        -   `milesPerKilometer: number = 0.621;`
        -   `name: string;`
        -   `speedMph: number;`
    b.  Constructor
        -   `name` is the first parameter and it MUST be a string.
        -   `speedMph` is the second parameter and it MUST be a number.
        -   Sets the class properties using `this.name` and
            `this.speedMph`.

    ::: admonition
    Note

    Once you complete the constructor, be sure to remove the variables
    you defined in part 1 (`spacecraftName`, `milesPerKilometer`, and
    `speedMph`.
    :::

2.  Move the function `getDaysToLocation`, defined in Part 3, into the
    `Spacecraft` class.

    a.  Remember to place the function after the constructor.
    b.  Update the function to reference the class properties
        `this.milesPerKilometer` and `this.speedMph`.

3.  Create an instance of the `Spacecraft` class.

    a.  `let spaceShuttle = new Spacecraft('Determination', 17500);`

4.  Print out the days to Mars.

    a.  Use template literals,
        `${spaceShuttle.getDaysToLocation(kilometersToMars)}` and
        `${spaceShuttle.name}`.

5.  Print out the days to the Moon.

    a.  Use template literals,
        `${spaceShuttle.getDaysToLocation(kilometersToTheMoon)}` and
        `${spaceShuttle.name}`.

6.  Use the terminal in VSCode to recompile your `.ts` file, then run
    the `.js` file again.

**Terminal**

    $ tsc parts1-5.ts
    $ node parts1-5.js
       Determination would take 332.67857142857144 days to get to Mars.
       Determination would take 0.5683628571428571 days to get to the Moon.

`Check your solution <typescript-exercise-solutions4>`{.interpreted-text
role="ref"}

## Part 5 - Export and Import the SpaceLocation Class

1.  From the file tree in VSCode, open the `SpaceLocation.ts` file.

2.  Paste in the code provided below.

    a.  Notice the `export` keyword. That is what allows us to import it
        later.

    ``` {.js linenos=""}
    export class SpaceLocation {
       kilometersAway: number;
       name: string;

       constructor(name: string, kilometersAway: number) {
          this.name = name;
          this.kilometersAway = kilometersAway;
       }
    }
    ```

3.  Add the function `printDaysToLocation` to the `Spacecraft` class.

    a.  Notice that it takes a parameter of type `SpaceLocation`.

    ``` {.js linenos=""}
    printDaysToLocation(location: SpaceLocation) {
       console.log(`${this.name} would take ${this.getDaysToLocation(location.kilometersAway)} days to get to ${location.name}.`);
    }
    ```

4.  Import `SpaceLocation` into `parts1-5.ts`.

    a.  Paste `import { SpaceLocation } from './SpaceLocation';` to the
        top of `parts1-5.ts`.

5.  Replace the earlier `console.log` statements by using the class
    instance to print out the days to Mars and the Moon.

    ``` {.js lineno-start="47"}
    spaceShuttle.printDaysToLocation(new SpaceLocation('Mars', kilometersToMars));
    spaceShuttle.printDaysToLocation(new SpaceLocation('the Moon', kilometersToTheMoon));
    ```

6.  Use the terminal in VSCode to compile your `.ts` file, then run the
    `.js` file again.

**Terminal**

    $ tsc parts1-5.ts
    $ node parts1-5.js
       Determination would take 332.67857142857144 days to get to Mars.
       Determination would take 0.5683628571428571 days to get to the Moon.

`Check your solution <typescript-exercise-solutions5>`{.interpreted-text
role="ref"}

## Sanity Check

The `typescript-lc101-projects` repository has two branches\-\--`master`
and `solutions`. \'Nuff said.
