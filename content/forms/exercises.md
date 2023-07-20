# Exercises: Forms

Hello programmer, we need you to make a Rocket Simulation form.

## Form Data

This is the kind of data the Rocket Simulation form will need to
process.

::: {#exercises-forms-data-table}
  Display Name                   Input Type   Input Name            Possible Values
  ------------------------------ ------------ --------------------- -------------------------------------------------------------------
  Test Name                      text         `testName`            No limitations
  Test Date                      date         `testDate`            Date format mm/dd/yyyy
  Rocket Type                    select       `rocketType`          Brant, Lynx, Orion, Terrier
  Number of Rocket Boosters      number       `boosterCount`        A positive number less than 10
  Wind Rating                    radio        `windRating`          No Wind: with value 0, Mild: with value 10, Strong: with value 20
  Use production grade servers   checkbox     `productionServers`   on or off

  : Data Fields for the Rocket Simulation Form
:::

## Form Display

Your completed simulation form will look roughly like this:

![](figures/rocket-simulation-example.png)

**Submitted Values**

    testName=Moon+Shot
    testDate=2020-07-16
    rocketType=Lynx
    boosterCount=3
    windRating=10
    productionServers=on

## Starting Codebase

Code your solution in [this
repl.it](https://repl.it/@launchcode/Exercises-rocket-simulation).

## Instructions {#exercises-forms-instructions}

Please follow the steps below and good luck!

1.  Create a `<form>` with these attributes.

    a.  Set `method` to `"POST"`
    b.  Set `action` to
        `"https://handlers.education.launchcode.org/request-parrot"`

    `Check your solution <forms-exercise-solutions1>`{.interpreted-text
    role="ref"}.

2.  Add a `<label>` and `<input>` for Test Name to the `<form>`.

    a.  `<label>Test Name <input type="text" name="testName"/></label>`.

3.  Can you submit the form now? What is missing?

    `Check your solution <forms-exercise-solutions3>`{.interpreted-text
    role="ref"}.

4.  Add a `<button>Run Simulation</button>` to the `<form>`.

5.  Enter a value into the \"testName\" input and submit the form.

    a.  Was the value properly submitted to the form handler?

    `Check your solution <forms-exercise-solutions5>`{.interpreted-text
    role="ref"}.

6.  Repeat steps 2 and 5 for the remaining data fields from the
    `data table <exercises-forms-data-table>`{.interpreted-text
    role="ref"}.

    a.  Pay attention to the input types and possible options.
    b.  Don\'t forget to add a `<label>` for each input.

## Bonus Mission

Use an event handler and the *submit* event to validate that all inputs
have values. Do NOT let the form be submitted if inputs are empty.
