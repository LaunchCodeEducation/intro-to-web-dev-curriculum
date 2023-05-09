---
title: "Exercises"
date: 2023-04-12T16:25:46-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Time to make a React app to share a hobby you love with your friends and family.

1. Create a new application called `exercises` in the `part3` directory in the `react-exercises-and-studios` repo.
1.In `App.js`, remove the content from the `<div className="App">` element and replace it with an `h1` heading that says "My Hobby: " with your hobby coming after the colon.
1. Create a new `components` directory in `src`.
1. Create a new file called `Introduction.js` in `components` and inside create a new functional component called `HobbyIntroduction`.
1. This functional component return a `div` that contains the following:

   1. An `h2` heading that that says something to the effect of "3 Fun Facts About this Hobby".
   1. An ordered list that contains three facts that you want others to know about your chosen hobby.

1. Call the new `HobbyIntroduction` component under your `h1` heading in `App.js`.
1. Run the application to see your new fun facts! Once you are satisfied, turn off the server so we can practice with state.
1. Inside `src`, create a new file called `data.json`. We are going to use this file to make a small gallery of images of projects or plans you have for your hobby. Inside this file, set up a new list of JSON objects called `projects`. Your list should contain 5 JSON objects and each one should have 4 properties that make sense with what your hobby is.
1. Create a new file called `Projects.js` in `components`. This file will hold a functional component called `MyProjects`.
1. Import the data from `data.json` and `useState` from `'react'` at the top of `Projects.js`.
1. Inside the `MyProjects` component, start by setting up a state variable for the index so we can loop through our list of projects. You can do this with the following code: `const [index, setIndex] = useState(0);`.
1. Now we need to set up some local variables and a return statement. 

   1. First, set up a JavaScript variable that contains your list from `data.json`. Then set up a variable that contains the item in that list at the position determined by `index`.
   1. Inside `return`, set up a button that contains the text, "Next". Set the `onClick` attribute to `{handleClick}`. 
   1. Below your button, add HTML that will nicely display all four properties of your JSON objects.

1. Finally, above the return statement, we need to set up `handleClick` like so:

   ```jsx
   function handleClick() {
      if (index < data.projects.length-1)
      {
         setIndex(index + 1);
      }
      else 
      {
         setIndex(0);
      }
   }
   ```

1. Return to `App.js` and call the completed `MyProjects` component below `HobbyIntroduction`. Run the application to see your new gallery! Hit the *Next* button to see state in action!