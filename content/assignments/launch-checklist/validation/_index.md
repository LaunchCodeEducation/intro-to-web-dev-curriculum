---
title: "Task 2: Adding Validation"
date: 2023-07-07T12:55:09-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Adding Alerts

Now, let's add validation to notify the user if they forgot to enter a value for any one of the fields.

<!-- TODO: Add link back to Forms chapter -->

This process is going to look similar to the validation section in the chapter on forms. Add an alert to notify the user that all fields are required.

You also want to make sure that the user entered valid info for each of the fields.
Valid information for the fields means that the user submits a value that is easily converted to the correct data type for our fellow engineers.
The pilot and co-pilot names should be strings and the fuel level and cargo mass should be numbers.
To do this, complete the helper function in your `scriptHelper.js` called `validateInput()`.
`validateInput()` should take in a string as a parameter and return `"Empty"`, `"Not a Number"`, or `"Is a Number"` as appropriate.
In `scriptHelper.js`, you will use `validateInput()` to complete the `formSubmission()` function.
`formSubmission()` will take in a `document` parameter and strings representing the pilot, co-pilot, fuel level, and cargo mass.
Using the values in those strings and the `document` parameter for your HTML document, update the shuttle requirements as described below.
Make sure to call your `formSubmission()` function at the appropriate time in your `script.js` file!

{{% notice blue "Note" "rocket" %}}

   If you want to check if something is `NaN`, you cannot use `==` or `===`.
   Instead, JavaScript has a built-in method called `isNaN(value)` that returns `true` if `value` is `NaN` and `false` if `value` is not `NaN`.

{{% /notice %}}

## Updating Shuttle Requirements

The list of shuttle requirements, the `div` with the id `faultyItems`, should be updated if something is not ready for launch. 
Using template literals, update the `li` elements `pilotStatus` and `copilotStatus` to include the pilot's name and the co-pilot's name.

If the user submits a fuel level that is too low (less than 10,000 liters), change `faultyItems` to `visible` with an updated fuel status stating that there is not enough fuel for the journey.
The text of the `h2` element, `launchStatus`, should also change to "Shuttle not ready for launch" and the `color` should change to red.

If the user submits a cargo mass that is too large (more than 10,000 kilograms), change the list to `visible` with an updated cargo status stating that there is too much mass for the shuttle to take off.
The text of `launchStatus` should also change to "Shuttle not ready for launch" and the `color` should change to red.

If the shuttle is ready to launch, change the text of `launchStatus` to green and display "Shuttle is ready for launch".

{{% notice blue "Note" "rocket" %}}

The autograder will check if your CSS is set to just red or green. While we normally encourage you to be creative, in this case, we ask that you only use `"red"` or `"green"` for the autograder.

{{% /notice %}}
