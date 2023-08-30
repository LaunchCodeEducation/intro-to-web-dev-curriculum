---
title: "Studio: Loops"
date: 2023-08-28T09:21:11-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Now that we've launched our shuttle, let's use loops (iteration) to
automate some tasks.

Open `loops/studio` in `javascript-projects`. Before you dive in, you might notice that we have several files and folders inside.
Your work will go into `solution.js`, but please feel free to explore the program and please don't edit anything outside `solution.js`. To get started, run the command. `npm install`, in your terminal.

## Part A: Put dinner together

1. First, inside `solution.js`, use the variables provided to store the following arrays.

   - Protein options:
   ```console
   ['chicken', 'pork', 'tofu', 'beef', 'fish', 'beans']
   ```

   - Grain options:
   ```console
   ['rice', 'pasta', 'corn', 'potato', 'quinoa', 'crackers']
   ```

   - Vegetable options:
   ```console
   ['peas', 'green beans', 'kale', 'edamame', 'broccoli', 'asparagus']
   ```

   - Beverage options:
   ```console
   ['juice', 'milk', 'water', 'soy milk', 'soda', 'tea']
   ```

   - Dessert options
   ```console
   ['apple', 'banana', 'more kale', 'ice cream', 'chocolate', 'kiwi']
   ```


2. Inside of `mealAssembly()`, write a `for` loop to assemble `numMeals` meals.

   1. The meals must include one item from each category in the `pantry` array.

   {{% notice green "Tip" "rocket" %}}
   The computer needs to know how many crew members to prepare food for and what ingredients. Consider creating a nested loop that will create a meal for each crew member and then add it into a larger collection of meals.
   {{% /notice %}}

   2. Each ingredient can only be used ONCE.
   3. Add each meal to the `meals` array once it is assembled.
   4. To test your own solution, scroll down to another function defined in this file called `runProgram()`. Uncomment the lines that call the `mealAssembly` function and print the result. Run the command `node solution` to see how your work is progressing.

## Part B: Collect User Input

Update `askForNumber()` to add user input and validation.

1. Using a `while` loop, ask the user to select the number of meals to assemble. Validate the input to make sure it is an integer from 1 - 6.
2. Save the result to the `numMeals` variable returned by the function.
3. Test your solution to this part by returning to the `runProgram()` function in the file and uncommenting the section labelled for testing Part B. Run `node solution` to see the result.

## Checking Your Work

If you want to make sure that you have checked all the boxes, run the following command in your terminal.

```console
npm test
```

This command runs the Jest tests that are checking your work for you. If you have a test that fails, check out the name of the test to get a hint as to what you are missing.
If you need a refresher on how running the tests works, check out the [article]({{< relref "../../../assignments/github-actions" >}}) on testing your code.

## Bonus Mission

Working and living aboard this amazing space shuttle requires you to pay the utmost attention to cybersecurity.
Once you are done working on the meal system, you are prompted to create a new password that will be used for the next 24 hours.
Having run out of strong password ideas, your shuttle captain has encouraged you to make a password generator for yourself.

Write your code inside `generatePassword()`.

1. Construct a `for` loop that combines the two strings together, alternating the characters from each source, and saves the combined string to the `code` variable.

   {{% notice blue "Example" "rocket" %}}

   1. If `string1 = "1234"` and `string2 = "5678"`, then the output will be "15263748".
   1. If `string1 = "ABCDEF"` and `string2 = "notyet"`, then the output will be "AnBoCtDyEeFt".
   1. If `string1 = "LoOt"` and `string2 = "oku!"`, then the output will be "LookOut!".

   {{% /notice %}}