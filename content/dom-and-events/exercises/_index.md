---
title: "Exercises: The DOM and Events"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

Time to make a flight simulator for your fellow astronauts! The provided HTML and JavaScript files can be used for all of the exercises. For each exercise,
the requirements and desired effect of the events is listed.

{{% notice blue Note "rocket" %}}
The following files can be found within your `javascript-projects/dom-and-events/exercises` directory.
{{% /notice %}}

1. When the *Take off* button is clicked, the text `The shuttle is on the ground` changes to `Houston, we have liftoff!`. The *Take off* button has an `id="liftoffButton"` attribute.

   {{% expand "Check Your Solution" %}}
   ```javascript
   button.addEventListener('click', event => {
      paragraph.innerHTML = 'Houston! We have liftoff!';
   });
   ```
   {{% /expand %}}

1. When the user's cursor goes over the *Abort Mission* button, the button's background turns red. The *Abort Mission* button has `id="abortMission"`.
1. When the user's cursor *leaves* the *Abort Mission* button, the button's background returns to its original state 

{{% notice green Tip "rocket" %}}
Setting the background color to the empty string, `""`, will force it to revert to the default browser styles.
{{% /notice %}}

   {{% expand "Check Your Solution" "rocket" %}}
   ```javascript
   missionAbort.addEventListener("mouseout", function( event ) {
      event.target.style.backgroundColor = "";
   });
   ```
   {{% /expand %}}

1. When the user clicks the *Abort Mission* button, make a confirmation window that says `Are you sure you want to abort the mission?`. If the user confirms that they want to abort, the text changes to `Mission aborted! Space shuttle returning home`.