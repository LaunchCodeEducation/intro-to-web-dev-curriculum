---
title: "Studio"
date: 2023-05-9T11:39:25-05:00
draft: false
weight: 3
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: Sally Steuterman # update any time edits are made after review
lastEditorGitHub: gildedgardenia # update any time edits are made after review
lastMod: 2023-10-19 # UPDATE ANY TIME CHANGES ARE MADE
---

In this studio, you will make a second Pinterest-inspired application.  This studio will add conditional rendering and the `map` function to the project.  

The app you complete in this studio will have the following functionality:
   1. A star rating component that can be updated to display 0 - 5 stars.
   1. The ability to mimic the Save vs Saved button on a Pinterest pin using conditional rendering.
   1. Displaying specific recipe information using the `map` function and a JSON file.
   1. CSS styling has been created for this project. The instructions will let you know what and how to style elements.  

## Getting Started

1. Check out the application in the `part2/studio` directory from the [exercises and studio](https://github.com/LaunchCodeEducation/react-exercises-and-studios) repo.

1. Explore the codebase.  
   1. Look at the `App` function. 
      1. You can see the list of components.  
   
         ```react{linenos=table,hl_lines=[],linenostart=9}
         export default function App() {
            return (
               <>
                  <RecipeImage />
                  <RecipeName />
                  <RateARecipe rating={5} />
                  <Button saveButton={true} />
                  <AuthorInfo />
                  <IngredientList />
               </>
            );
         }  
         ```

      1. Notice that both `RateARecipe` and `Button` have variables.  `RateARecipe` takes a number and `Button` takes a boolean.
      
      We will be providing the code (hard coding) for this app to render conditionally.  Keep that in mind as you work on this studio. Test things by changing these variables here.

   1. In the `components` folder:  
      1. Open the `recipe.json` file and populate the values with data from a recipe you find online. This can be the same recipe you used in Part 1 or a new recipe. 
      1. Save the file.

## Part 1: `RateARecipe`

*Desired Output:* The `RateARecipe` function should return 0-5 stars. The number of stars rendered will be determined by passing the function an argument. 

1. Open the `RateARecipe.jsx` file inside the `components` folder.  You will see an array of star emojis.  These will be our rating system for the Pin.

1. Inside `RateARecipe` create a new function, that will also take props.  
   1. Let's name it `GiveRating`.  This function will return the number of stars passed to `RateARecipe`.  
   1. `GiveRating` will use the number passed to `RateARecipe` to index through the `stars` array.  You will need to apply some math to make the array output match the number of stars rendered.
   1. Return the rating at least an `<h3>` level header. 

      ```react{linenos=table,hl_lines=[],linenostart=4}
      function GiveRating() {
         return <h3>{stars[props.rating - 1]}</h3>;
      }
      ```
   `GiveRating` is nested inside `RateARecipe` and is returning the number of stars.  Next, let's add a conditional to make sure a user only provides a number between 1-5.

1. Create a ternary that checks the value of `props`.  If the number is between 1 and 5, then render `GiveRating` else render `null`.  
1. Test this in the `App` function by updating the value of `rating`.


## Part 2:  Buttons

Let's explore the buttons!  A Pinterest pin has a red button with the word "Save" printed on it. When a user clicks that button, it switches to black with the word "Saved". 

There are 3 components for the buttons.  
- `SaveButton` and `ClickedButton` render the buttons in the browser.  Both of these components contain an alert to verify we can click each button.
- The `Button` component will render either button based on a conditional. We will be using a boolean in the `App` function to serve as our "click"

### SaveButton

_Desired Output_: A Red button with rounded corners which reads "Save" in white letters.  If you hover over it, the red changes to a darker red.  When you click the button, a pop appears that reads "You are saving this pin!".

This button has already been created.  You can use its code to help you create `ClickedButton` component.

1. Open the `SaveButton` file and explore the code. An alert has been added to demonstrate that you clicked the button.  
1. When you click the Save button on a Pinterest pin, it will share a notification that you Saved the pin to a board.  
1. The `button` class contains an `id` for the CSS needed to make the button red. The CSS has already been created in the `styling.css`. The styling also changes when you hover over the button. It's unique to this button.

{{% notice green "Tip for Testing" "rocket" %}} 
 
If you want to check how `SaveButton` works, you can nest it inside the `App` function.  You can try this with any of the components you are creating.

Be sure to remove it once you have a working `Button` component.

{{% /notice %}}

### ClickedButton

_Desired Output_: A black button with rounded corners.  The word has changed to "Saved". When you click on this button a message about removing the pin appears.

1. Move into `ClickedButton.jsx`. It should function like the Save button, but it should display "Saved" instead of "Save", and be black instead of red. 
1. For the styling, you can apply `clickedButton` as the `id`. This is found in the CSS styling which will need to be imported.  
1. It should also have an alert that lets a user know that when you click it the pin is removed from the board. 

### Button

_Desired Output_:  Returns either `SaveButton` or `ClickedButton` based on the boolean value.

This function will hold the logic that will determine which button will appear in the browser.  
You will need to create a conditional that will render `SaveButton` or `ClickedButton`.
   1. `Button` function should take an argument, such as `props`. 
   1. Create a variable that defines the `props`. Name the variable  `saveButton`.  

      ```react{linenos=table,hl_lines=[],linenostart=5}
      const saveButton = props.saveButton;
      ```

   1. Create a conditional that does the following:   
      1. If the `saveButton` variable is `true`, then `SaveButton` will render
      1. else `ClickedButton` will appear.  
   1. In the `App` function, the `Button` component has `saveButton` equal to `true`.  
   1. Test the conditional by changing `saveButton` in the `App` function to `false`.

## Part 3: Add the Recipe Data

The remaining components will be using the `recipe.json` file.  You will need to import this file into each component.  We will also use the `map` function to find the desired keys.

### Recipe Name

_Desired Output_: This function needs to return the recipe name as an `<h1>` level header.

1. Open the `RecipeName` component.
1. Render the recipe's name as an `<h1>` level header.  
1. `return` the `recipeName` variable.  

### Image

_Desired Output_:  Returns the image of the recipe from the JSON.

1. Import the recipe JSON file.
1. Use the `map` function to find the `recipeImage`.  
   1. Use the `<img>` tag.  You can pass the recipe name to the alt text value.
   1. Styling has been created for the image. If you would like to apply it set the `className` equal to `recipeImage`. 
      ```react{linenos=table,hl_lines=[],linenostart=4}
      function RecipeImage() {
         const recipeImage = recipedata.map((data) => (
            <div key={data.name}>
            <img src={data.recipeImage} alt={data.name} className="recipeImage" />
            //component continues
      ```
1. Return `recipeImage` inside its own `<div>`.

### Ingredient Lists

_Desired Output_:  Create an unordered list of ingredients.

This component will map over a list of ingredients.  The ingredients are contained within an array inside our JSON object. We will create a `map` function to iterate through the array of ingredients.

1. Import the recipe.
1. `IngredientsList` will return a single `<div>` that holds an `<h3>Ingredients</h3>` header.
1. Create a list object by placing our map inside curly braces.  In the other components, we used a variable to hold our map output.  In this component, we will return the list as we render it.
1. The `map` function will iterate through the ingredients using `id` as a key. 

### Author Info

_Desired Output_: A single component that returns the author's name, image, and URL.  There is CSS for the image that you can set if you desire.

1. Import the recipe and styling.
1. Let's start by creating a variable that will return the author's name.  Create a `<div>` that returns the value of the `author`.  You can set the `key` equal to the `name`. 
1. Create a second variable that will use the map function to return the author's image.
   1. Set the alt text equal to the author's name.
   1. Apply the `authorImage` as the `className`.
1. Finally, create the final variable that will host the URL.  Return the link using the `<a>` tag.  The URL can be the context between the opening and closing tags.
1. Return all variables in a final `<div>`.  

   ```react{linenos=table,hl_lines=[],linenostart=18}
      return (
         <div>
            {recipeAuthorImage}
            {recipeAuthor}
            {recipeWebsite}
         </div>
      );
   ```

## Wrapping Up

**Congrats!** You've finished the studio!  Make sure that you `stage`, `commit`, and `push` your work up to GitHub.
