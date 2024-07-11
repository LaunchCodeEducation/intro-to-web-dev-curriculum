---
title: "Exercises: Forms"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

Hello programmer, we need you to make a Rocket Simulation form. 

## Form Data

This is the kind of data the Rocket Simulation form will need to process.

# Data Fields for the Rocket Simulation Form

| Display Name               | Input Type | Input Name         | Possible Values                               |
|---------------------------|------------|--------------------|-----------------------------------------------|
| Test Name                  | text       | `testName`         | No limitations                                |
| Test Date                  | date       | `testDate`         | Date format mm/dd/yyyy                       |
| Rocket Type                | select     | `rocketType`       | Brant, Lynx, Orion, Terrier                   |
| Number of Rocket Boosters  | number     | `boosterCount`     | A positive number less than 10                |
| Wind Rating                | radio      | `windRating`       | No Wind: with value 0, Mild: with value 10, Strong: with value 20 |
| Use production grade servers | checkbox  | `productionServers` | on or off                                    |

## Form Display

Your completed simulation form will look roughly like this:

![Rocket simulation form with all input fields filled out](pictures/rocket-simulation-example.png?classes=border)

**Submitted Values**

```console
testName=Moon+Shot
testDate=2020-07-16
rocketType=Lynx
boosterCount=3
windRating=10
productionServers=on
```

## Starting Codebase

Code your solution within the `javascript-projects/user-input-with-forms/exercises` directory.

## Instructions

Please follow the steps below and good luck!

1. Create a `<form>` with these attributes.
   1. Set `method` to `"POST"`
   1. Set `action` to `"https://handlers.launchcodelearning.org/request-parrot"`

   {{% expand "Check Your Solution" %}}
   ```html
   <form action="https://handlers.launchcodelearning.org/request-parrot" method="POST">
      // the rest of your form fields go in here //
   </form>
   ```
   {{% /expand %}} 

2. Add a `<label>` and `<input>` for Test Name to the `<form>`.
   1. `<label>Test Name <input type="text" name="testName"/></label>`.

3. Can you submit the form now? What is missing?

{{% expand "Check Your Solution" %}}
You can't submit the form with a button to submit it!
{{% /expand %}}

4. Add a `<button>Run Simulation</button>` to the `<form>`.
5. Enter a value into the "testName" input and submit the form.
   1. Was the value properly submitted to the form handler?

{{% expand "Check Your Solution" %}}

Yes! At this point, your form should be able to handle input into the "testName" field.
{{% /expand %}}

6. Repeat steps 2 and 5 for the remaining data fields from the [data table]({{% relref "#data-fields-for-the-rocket-simulation-form"  %}}). 
   1. Pay attention to the input types and possible options.
   1. Don't forget to add a `<label>` for each input.

## Bonus Mission

Use an event handler and the *submit* event to validate that all inputs have
values. Do NOT let the form be submitted if inputs are empty.
