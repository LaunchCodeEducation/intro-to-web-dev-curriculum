---
title: "Studio"
date: 2023-04-12T16:25:46-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas 
reviewerGitHub: icre8FreeCode 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Let's add some additional functionality to our recipe app! To get started, check out the starter code for the studio in the `part3` directory on the `main` branch of [react-exercises-and-studios](https://github.com/LaunchCodeEducation/react-exercises-and-studios). The starter code includes all the components you will need and in `App.js`, all the components are laid out for you. However, if you run the code, you will find lots of warnings and errors. Time to check out the different components and make use of what you have learned about state!

## `Recipe.js`

In the `components` directory, you will find `Recipe.js`. This file contains some familiar code to us so start here with editing your app. Pick out a recipe you think would be fun for the studio. Make note of the following:

1. The recipe's title
1. A short description of the recipe
1. Five ingredients used in the recipe
1. A link to a photo from the recipe
1. A link to a photo of the recipe's author
1. The author's name 
1. A link to the author's website

With all this information at hand, review `Recipe.js` and add each piece of information where it is appropriate. None of this information belongs in another file so you do not need to check out any of the other components just yet. When you feel like you have put everything where it should go, run the app again. It should still have some warnings and errors, so it is time to move on to the next component.

## `BoardAssignment.js`

Staying in the `components` directory, turn your attention to `BoardAssignment.js`. First, brainstorm three boards that the recipe you chose might belong to. 

1. Currently, `boards` is an empty array. `boards` should contain three objects representing the three boards that you just brainstormed. Each object must contain a `label` property and a `value` property. We will be using these three objects to create a dropdown menu that a user can select the board they want to save the recipe to.
1. With all the options we want to display in our dropdown in `boards`, we need to use `map()` to set up an `<option>` tag for each item in `boards`. The `<option>` tags go between `<select>` and `</select>` and have this general structure: `<option value={appropriate value}>{appropriate label}</option>`. This is just a dropdown so now we need to handle whatever the user ends up choosing.
1. In the `<select>` tag, the starter code comes with the necessary attributes for dealing with the user's selection. However, `handleChange()` is empty and `boardName` is never declared. Start with `boardName` by declaring it as a state variable with a state setter function called `setName()` and making use of the `useState` hook. Set the initial value of `boardName` to `'no boards yet!'`.
1. `handleChange()` is the other key part in changing the state of `boardName`. Update the value of `boardName` to the value of `event.target.value`.

While we have set up `BoardAssignment` to update some HTML so the user's selection is displayed, the app will still have issues when run. Let's work on the final component so we can get this app running perfectly!

## `StatusChange.js`

Time to finish the final component! In `StatusChange.js`, we have some empty methods and some HTML, but we have even more to do.

1. Use `useState` to set up two state variables: `notes` and `recipeStatus`. The initial value of `notes` should be an empty string and the initial value of `recipeStatus` should be `false`.
1. For `handleChange()`, update the value of `notes` to `event.target.value`.
1. For `handleSubmit()`, first use `event.preventDefault()` to make sure the user's notes aren't immediately lost and update the value of `recipeStatus` to `true`. 
1. Update the HTML in the `return` statement so that it uses the value of `notes` and displays a different message if `recipeStatus` is `true`.

Run the application! You should be able to change the board the recipe belongs to and add notes to the recipe once you have tried it out yourself.

## Submit Your Work

Once you are done with the studio, push your work to Github and submit the link to your repo on Canvas.