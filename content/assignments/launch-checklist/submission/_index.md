---
title: "Task 4: Submitting Your Work"
date: 2023-07-07T12:55:09-05:00
draft: false
weight: 6
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer:  # to be set by the page reviewer
reviewerGitHub:  # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## The End Result

After you implement everything, the following form submission would result in the proper updates to the `launchStatus` and `faultyItems` list.

![Image showing the user is submitting a form with Chris as the pilot, Blake as the co-pilot, 890 liters as the fuel level, and 178 kilograms as the cargo mass.](pictures/form-fields-ready.png)

With only 890 liters of fuel, the status of the launch becomes red and states that the shuttle is not ready. 
The list has also updated to indicate that that is not enough fuel for the shuttle to launch.

![Image showing the updates to the faulty items list and the launch status.](pictures/form-submission-result.png)

If the user forgets to enter the cargo mass, then an alert pops up letting the user know that all fields are required.

![Image showing an alert pop up stating that all fields are required.](pictures/form-fields-required.png)

If the user switches up the information that needs to go in the fields, then an alert pops up letting the user know that they have tried to enter invalid information.

![Image showing an alert pop up stating that some fields have invalid information.](pictures/form-fields-invalid.png)

## Submission

Even if everything is working perfectly with your site, the autograder may still be counting something as wrong.
Here are some steps you can take to make sure your great work is counted as such!

1. Make sure that all of your methods are complete in `scriptHelper.js`! The autograder needs to check your logic for each of the methods.
   `script.js` should contain calls to these functions.
1. If the tests are failing, make sure that you did not modify `bundle.js` or remove `<script src = "bundle.js"></script>` from `index.html`.
   The autograder needs `bundle.js` linked as a script in `index.html` in order to run properly.