---
title: "Studio"
date: 2023-05-9T11:39:25-05:00
draft: false
weight: 3
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In this studio you will make a second Pinterest inspired Pin.  This studio will add conditional rendering and the `map` function to the project.  


The app you complete in this studio will have the following functionality:
   1. A star rating component that can be updated to display 0 - 5 stars.
   1. A component that mimics the Save vs Saved button on a Pinterest pin using conditional rendering
   1. Displaying the recipe information using the `map` function and a json file.


## Getting Started

1. Fork and clone the [starter code ADD LINK](). //TODO: Link to starter code
1. Explore the codebase.  
   1. Look at the `App` function. 
      1. You can see the list of components.  
      1. You will declare variables in the `RateARecipe` and `Button` apps.  
   1. In the `components` folder:  
      1. Open the `recipe.json` file and populate the values with data from a recipe you find online. This can be the same recipe you used in Part 1 or a new recipe. 
      1. Save the file.

## Part 1: `RateARecipe`

1. Open the `RateARecipe.js` file inside the `components` folder.  You will see an array of star emojis.  These will be our rating system for the Pin.
1. The `RateARecipe` function should return 0-5 stars. The number of stars rendered will be determined by passing the function an argument. 
1. Use a conditional to check that the number provided is between 1-5.  
1. Import and call `RateARecipe` from the `App` function.  Pass it a number to declare the star rating.

## Part 2:  Buttons

Let's explore the button feature.  A Pinterest pin has a red button with the word "Save" printed on it. When a user clicks that button, it switches to black with the word "Saved". We are going to use conditionals to render these buttons. 

**SavedButton**
1. Open the `SaveButton` file and explore the code. An alert has been added to demonstrate that you clicked the button.  
1. When you click the Save button on a Pinterest pin, it will share a notification that you Saved the pin to a board.  
1. The `button` class contains an `id` for the CSS needed to make the button red. The CSS has already been created in the `App.css`. The styling also changes when you hover over the button. It's unique to this button.

**ClickedButton**
1. Move into `ClickedButton.js`. It should function like the Save button, but it should display "Saved" instead of "Save", and be black instead of red. 
1. For the styling, you can apply `clickedButton` as the `id`. This is found in the CSS styling which will need to be imported.  
1. It should also have an alert that lets a user know that when you click it the pin is removed from the board. 

**Button**
This function will hold the logic that will determine which button will appear in the browser.  

You will need to create a conditional that will render `SaveButton` or `ClickedButton`.
   1. `Button` function will need to take an argument, such as `props`.  
   1. Declare a variable and set it equal to `props.saveButton`.
   1. If your variable is true, then `SaveButton` will render, else `ClickedButton` will appear.  
   1. In the `App` function, call `Button` and set `saveButton` as `true`.

## Part 3: Add the Recipe Data

The remaining components will be using the `recipe.json` file.

### Recipe Name

Open the `RecipeName` component.

This function needs to return the recipe name as an `<h1>` level header.

1. `map` through the `json` and pull out the name.
   1. There is no `id` key in our JSON file.  We can use any of the other keys.  Set the key = to  
   
   Since a `key` requires a unique val set as one of the keys in the `json` file
- `return` the name

### Image

- `map` through and pull out the image 

### Author Info

- `map` out and pull out author info
   - name
   - image (css)
   - website

### Ingredient Lists

- `map` to find the ingredients array
   - `map` inside the ingredients array