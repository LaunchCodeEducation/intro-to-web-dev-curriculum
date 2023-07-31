---
title: "Assignment 5: Launch Checklist"
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

Using our knowledge of forms, the DOM, and HTTP, the commanders of our favorite space shuttle program asked us to create a quick launch checklist.
We have four fields that need to be filled out with vital information: the pilot's name, the co-pilot's name, the fuel levels, and the mass of the cargo.

Our pilot, Chris, and the co-pilot, Blake, have been hard at work securing the cargo and filling the shuttle tank. All we need to do is use validation to ensure that we have all of the info for the space shuttle program and make sure no one prematurely launches the shuttle.

## Requirements

Create a Launch Checklist Form for astronauts to fill out in preparation for launch. The form should do the following:

1. Use `preventDefault()` to prevent a request from being sent out and the page reloading.
1. Validate the user-submitted data to ensure the following:

   1. The user entered something for every field.
   1. The user entered text for names and numbers for fuel and cargo levels.

1. With validation, update a list of what is currently ready or not ready for the shuttle launch.
1. Indicate what is good or bad about the shuttle and whether it is ready for launch by using the DOM to update the CSS.
1. Fetch some planetary JSON to update the mission destination with vital facts and figures about where the shuttle is headed. 

## Assignment Tasks

{{% children %}}
 