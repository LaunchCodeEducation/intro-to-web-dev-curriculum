---
title: "Coding with Objects"
date: 2023-08-31T13:16:22-05:00
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

## Booleans and Objects

Objects are not stored by their properties or by value, but by `reference`.
Storing something by reference means that it is stored based on its location
in memory. This can lead to some confusion when comparing objects.

{{% notice blue "Example" "rocket" %}}
   Let's see how this affects our zoo software! Surely, the zoo has more than one tortoise. The second tortoise is named Patricia!

   ```js {linenos=table}
      let tortoiseTwo = {
         species: "Galapagos Tortoise",
         name: "Patricia",
         weight: 800,
         age: 85,
         diet: ["pumpkins", "lettuce", "cabbage"],
         sign: function() {
            return this.name + " is a " + this.species;
         }
       };
   ```

   Because Pete and Patricia are members of the same species, are the same age, and have the same diet, you might notice that many of their properties are equal, but some are not.
   Pete weighs more than Patricia and of course, they have different names!

   For this example, we will only keep the `species` and `diet` properties.

   ```js {linenos=table}
      let tortoiseOne = {
         species: "Galapagos Tortoise",
         diet: ["pumpkins", "lettuce", "cabbage"]
      };

      let tortoiseTwo = {
         species: "Galapagos Tortoise",
         diet: ["pumpkins", "lettuce", "cabbage"]
      };

      console.log(tortoiseOne === tortoiseTwo);
   ```

   **Console Output**

   ```console
      false
   ```

   The objects contain properties that have the same keys and equal values.
   However, the output is `false`.

{{% /notice %}}

Even though `tortoiseOne` and `tortoiseTwo` have the same keys and values,
they are stored in separate locations in memory. This means that even though
you can compare the properties in different objects for equality, you cannot
compare the objects themselves for equality.

## Iterating Through Objects

We can iterate through all of the values in an object, much like we would do
with an array. We will use a for loop to do that, but with a slightly
different structure. `for...in` loops are specifically designed to loop
through the properties of an object. Each iteration of the loop accesses a key
in the object. The loop stops once it has accessed every property.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=table}
      let giraffe = {
        species: "Reticulated Giraffe",
        name: "Cynthia",
        weight: 1500,
        age: 15,
        diet: "leaves"
      };

      for (item in giraffe) {
         console.log(item + ", " + giraffe[item]);
      }
   ```

   **Console Output**

   ```console
      species, Reticulated Giraffe
      name, Cynthia
      weight, 1500
      age, 15
      diet, leaves
   ```

   In this example, `item` is a variable that holds the string for each key. It is updated with each iteration of the loop.

{{% /notice %}}

{{% notice blue "Note" "rocket" %}}

   Inside a `for..in` loop, we can only use bracket syntax to access the property values.

{{% /notice %}}

{{% notice blue "Example" "rocket" %}}

   Open the `chapter-examples` directory in the `javascript-projects/objects-and-math` directory. 
   Inside `ForInLoop.js`, write a `for..in` loop to print to the console the values in the `tortoiseOne` object. 

{{% /notice %}}

## Objects and Functions

Programmers can pass an object as the input to a function, or use an object as
the return value of the function. Any change to the object within the function
will change the object itself.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=table}
      let giraffe = {
        species: "Reticulated Giraffe",
        name: "Cynthia",
        weight: 1500,
        age: 15,
        diet: "leaves"
      };

      function birthday(animal) {
          animal.age = animal.age + 1;
          return animal;
      }

      console.log(giraffe.age);

      birthday(giraffe);

      console.log(giraffe.age);
   ```

   **Console Output**

   ```console
      15
      16
   ```

   On line 16, when the `birthday` function is called, `giraffe` is passed in as an argument and returned. After the function call, `giraffe.age` increases by 1.

{{% /notice %}}

## Check Your Understanding

{{% notice green "Question" "rocket" %}}

   What type of loop is designed for iterating through the properties in an object?

{{% /notice %}}

<!-- for in loop -->

{{% notice green "Question" "rocket" %}}

   Given the following object definitions, which statement returns `true`?

   ```js {linenos=table}
      let tortoiseOne = {
         age: 150,
         species: "Galapagos Tortoise",
         diet: ["pumpkins", "lettuce", "cabbage"]
      };

      let tortoiseTwo = {
         age: 150,
         species: "Galapagos Tortoise",
         diet: ["pumpkins", "lettuce", "cabbage"]
      };
   ```

   1. `tortoiseOne == tortoiseTwo`
   1. `tortoiseOne === tortoiseTwo`
   1. `tortoiseOne.age === tortoiseTwo.age`

{{% /notice %}}

<!-- 3 -->