---
title: "Studio: A Few of Your Favorite Recipes"
date: 2023-03-31T09:42:17-05:00
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

One reason we are learning React is because many top tech companies use it, including Pinterest. On Pinterest, we can create boards and save pins of new recipes, wedding decor concepts, and tips and tricks for crafts. When one clicks on the pin, they are taken to a detailed view which includes a photo, a description of the pin, and in the case of recipes, ingredients one needs for that recipe. Today, we are going to try our own take on this page using React and what we have learned about components. 

Before you start coding, find a recipe for some food you would like to eat! It can be any recipe, sweet or savory, but you should make sure that it meets the following:

1. The recipe is easily found online.
1. You can right-click on a photo of the completed item and get a valid URL of the image. 
1. You can right-click on a photo of the author and get a valid URL of the image.
1. The recipe includes at least 5 ingredients.

## Setting Up Your App

To get started coding, you need to first create an application.

1. Open up your `react-exercises-and-studios` repo and navigate into the `part1` directory.
1. Create a new React app named `studio` with the command: `npx create-react-app studio`.
1. Once your application is set up, run `npm start` to verify that your application runs and is ready to go.
1. Stop the server and start coding!

## The Components

First create inside `src`, a folder called `components`. Now tackle creating the components one-by-one.

### The `RecipeDescription` Component

1. Inside the `components` directory, make a new file called `Description.js`.
1. Create a new function called `RecipeAuthor()`. For now, this function may not work as expected, but we have more work to do! This function should meet the following requirements:

   1. Have no parameters.
   1. Have three local variables: `authorLink`, `authorPhoto`, and `authorName`.
   1. `authorLink` should contain the link to the recipe blog or if the author is not the owner of the blog, one of their social media profiles.
   1. `authorPhoto` should include a valid URL pointing to a photo of the author.
   1. `authorName` should contain the author's full name.
   1. Return something similar to the following:

   ```jsx
   return (
      <div className = {styles.recipeAuthorBlock}>
         <img src={authorPhoto} alt = "Reasonable alt text" className={styles.imageUpdates} />
         <div>
            <h3>{authorName}</h3>
            <a href={authorLink}>Blog name</a> 
         </div>
      </div>
   );
   ```

1. Create a new file in the `components` directory called `Description.module.css` and add the following CSS to this file.

   ```css
   .recipeAuthorBlock {
   display: flex;
   justify-content: space-evenly;
   }

   .imageUpdates {
      object-fit: contain;
   }
   ```

1. Return to `Description.js` and add this `import` statement: `import styles from './Description.module.css;`.
1. Add one more `import` statement: `import React from 'react';`
1. Add a class called `RecipeDescription` which extends `React.Component`. This class should have only a `render()` method which returns something similar to the following JSX:

   ```jsx
      <div> 
         <div>
            <h1>Recipe Title</h1>
            <p>Short recipe description</p>
         </div>
         <RecipeAuthor />
      </div>
   ```

1. At the bottom of `Description.js`, add `export default RecipeDescription;`.
1. Head over to `App.js` and remove what is *inside* the `<div>` element with `className="App"`.
1. Add a second `<div>` and inside that add `<RecipeDescription />` to call your new component. Add any necessary `import` statements. It should now look something like:

   ```jsx
   <div className="App">
      <div>
         <RecipeDescription />
      </div>
   </div>
   ```

1. Run your application! You should have a white screen that just includes your `RecipeDescription` component.

### The `RecipeIngredients` Component

1. Inside your `components` directory, create a new file called `Ingredients.js`.
1. Inside this file, add a new function called `RecipeIngredients()`. This function should include the following:

   1. An array containing the top 5 ingredients of your recipe.
   1. Return something similar to the following JSX:

   ```jsx
      <div>
         <h3>Recipe Ingredients</h3>
         <ul className = {styles.ingredientList}>
            <li>{ingredients[0]}</li>
            <li>{ingredients[1]}</li>
            <li>{ingredients[2]}</li>
            <li>{ingredients[3]}</li>
            <li>{ingredients[4]}</li>
         </ul>
      </div>
   ```

1. Now create a new file in the `components` directory called `Ingredients.module.css`. 
1. Add the following CSS to this new file:

   ```css
   .ingredientList {
      text-align: left;
   }
   ```

1. Return to `Ingredients.js` and add the following `import` statement: `import styles from './Ingredients.module.css';`.
1. If you didn't before, add `export default` in front of your `RecipeIngredients()` function declaration.
1. Head over to `App.js`.
1. Right below `<RecipeDescription />`, add `<RecipeIngredients />` and the necessary `import` statement.
1. Run your application! You should now see a list of ingredients below your recipe description.

### The `RecipePhoto` Component

1. Create a new file in `components` called `Photos.js`. 
1. Add a new function called `RecipePhoto()` and add something similar to the following JSX to your return statement with the correct URL to your chosen recipe's image:

   ```jsx
      <img src="valid URL to recipe photo" alt="recipe photo" className = {styles.imageUpdates} />
   ```

1. Add the following `import` statement to the top of your file: `import styles from './Description.module.css';`.
1. If you haven't already, add `export default` to your function declaraction.
1. Head over to `App.js` and import the `RecipePhoto` component. 
1. You will add `<RecipePhoto />` above the inner `<div>`, but inside `<div className="App">`. Wrap `<RecipePhoto />` and the inner `<div>` in another `<div>`. It should look like the following:

   ```jsx
   <div className="App">
      <div>
         <RecipePhoto />
         <div>
            <RecipeDescription />
            <RecipeIngredients />
         </div>
      </div>
    </div>
    ```

1. Now if you run your application, you will have all the info you need! Everything may look a little wonky. Let's fix it!

## Add some more CSS!

1. In `App.css`, add a CSS class to the bottom of the file.

   ```css
   .recipePhotoBlock {
      display: flex;
      justify-content: space-evenly;
   }
   ```

1. Return to `App.js` and add `className="recipePhotoBlock"` to the `<div>` that contains `<RecipePhoto />` and the innermost `<div>`.
1. Re-run the application to see the result!

## Submitting Your Work

Before you submit, check out the `solutions` branch to see an example of how the application should work.

1. Save your work and commit and push to your remote.
1. Submit the link to your remote repository on Canvas.