---
title: "Objects and Why They Matter"
date: 2023-08-31T13:16:22-05:00
draft: false
weight: 1
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

So far we have learned a lot about arrays, which are data structures that can hold many values.
**Objects** are also data structures that can hold many values. 

Unlike arrays, each value in an object has a name or **key** for reference purposes.
The pairing between a key and its value is called a **key/value pair**. 

Objects store as many key/value pairs as needed, and each value needs a key. Without a key, the value cannot be accessed or modified by the programmer.

![Diagram showing that objects are a collection of key/value pairs](pictures/object.png)

## Initializing Objects

When defining an object, we call the initialization an **object literal**.
Objects require three things for the definition: a name, a set of keys, and their corresponding values.

{{% notice blue "Note" "rocket" %}}

   Object literals use curly braces, `{}`, to enclose the key/value pairs.

{{% /notice %}}

Once we have these three things, we write an object literal like so:

```js
   let objectName = {key1:value1, key2:value2, key3:value3, ... };
```

If we have a lot of key/value pairs in our object, we can also put each one on a separate line!

```js
   let objectName = {
       key1: value1,
       key2: value2,
       key3: value3,
       .
       .
       .
   };
```

{{% notice orange "Warning" "rocket" %}}
   When putting the key/value pairs on separate lines, it is important to pay attention to spaces and tabs!
   Incorrect spacing or tab usage can result in a bug.
{{% /notice %}}

When defining an object, keep in mind that the keys can only be valid JavaScript strings.
The values can be any of the data types that we have previously discussed.

{{% notice blue "Example" "rocket" %}}
   Let's say that we want to create a small program for a zoo.
   We could create an object for storing the different data points about the animals in a zoo.
   We start with our first tortoise. His name is Pete! He is an 85 year old, 919 lb Galapagos Tortoise, who prefers a diet of veggies.
   Our object literal for all of this important data about Pete would be: 

   ```js {linenos}
   let tortoiseOne = {
         species: "Galapagos Tortoise",
         name: "Pete",
         weight: 919,
         age: 85,
         diet: ["pumpkins", "lettuce", "cabbage"]
   };
   ```

{{% /notice %}}

## Methods and Properties

A **property** of an object is a key/value pair of an object.
The property's name is the key and the property's value is the data assigned to that key.

A **method** performs an action on the object, because it is a property that stores a function.

{{% notice blue "Example" "rocket" %}}

   In the case of Pete, our zoo's friendly Galapagos Tortoise, the object `tortoiseOne` has several properties for his species, name, weight, age, and diet.
   If we wanted to add a method to our object, we might add a function that returns a helpful statement for the general public.

   ```js {linenos=table}
      let tortoiseOne = {
          species: "Galapagos Tortoise",
          name: "Pete",
          weight: 919,
          age: 85,
          diet: ["pumpkins", "lettuce", "cabbage"],
          sign: function() {
              return this.name + " is a " + this.species;
          }
       };
   ```

{{% /notice %}}

In the example above, on line 8, we see a keyword which is new to us.
Programmers use the `this` keyword when they call an object's property from within the object itself.
We could use the object's name instead of `this`, but `this` is shorter and easier to read.
For example, the method, `sign`, could have a return statement of `tortoiseOne.name + " is a " + tortoiseOne.species"`.
However, that return statement is bulky and will get more difficult to read with more references to the `tortoiseOne` object.


## Check Your Understanding

{{% notice green "Question" "rocket" %}}

   Which of the following is NOT a true statement about objects?

   1. Objects can store many values
   1. Objects have properties
   1. Objects have methods
   1. Keys are stored as numbers

{{% /notice %}}

<!-- 4, keys are supposed to be strings, not numbers -->

{{% notice green "Question" "rocket" %}}

   Which keyword can be used to refer to an object within an object?

   1. `Object`
   1. `let`
   1. `this`

{{% /notice %}}

<!-- 3, this is the correct keyword -->