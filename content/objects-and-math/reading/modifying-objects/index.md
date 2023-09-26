---
title: "Working with Objects"
date: 2023-08-31T13:16:22-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Accessing Properties

When using objects, programmers oftentimes want to retrieve or change the value of one of the properties.
To access the value of a property, you will need the object's name and the key of the property.

Programmers have two ways to access the value of property:

1. Bracket syntax
1. Dot notation

### Bracket Syntax

To access a property with bracket syntax, the code looks like: `object["key"]`.

### Dot Notation

To access a property with dot notation, the code looks like: `object.key`. Notice that the key is no longer surrounded by quotes. However, keys are still strings.

{{% notice blue "Note" "rocket" %}}

   Recall, the only restraint in naming a key is that it has to be a valid JavaScript string.
   Since a key could potentially have a space in it, bracket syntax would be the only way to access the value in that property because of the quotes.

{{% /notice %}}

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=table}
      let tortoiseOne = {
          species: "Galapagos Tortoise",
          name: "Pete",
          weight: 919,
          age: 85,
          diet: ["pumpkins", "lettuce", "cabbage"]
      };

      console.log(tortoiseOne["name"]);
      console.log(tortoiseOne.name);
   ```

   **Console Output**

   ```console
      Pete
      Pete
   ```

{{% /notice %}}

## Modifying Properties

A programmer can modify the value of a property by using either notation style.

{{% notice orange "Warning" "rocket" %}}

   Recall that mutability means that a data structure can be modified without making a copy of that structure.
   Objects are mutable data structures.
   When you change the value of a property, the original object is modified and a copy is NOT made.

{{% /notice %}}

{{% notice blue "Example" "rocket" %}}

   In our zoo software, we may want to update Pete's weight as he has gained 10 lbs.
   We will use both bracket syntax and dot notation for our software, but that is not a requirement!
   Feel free to use whichever one suits your needs and is easiest for you and your colleagues to read.

   ```js {linenos=table}
      let tortoiseOne = {
          species: "Galapagos Tortoise",
          name: "Pete",
          weight: 919,
          age: 85,
          diet: ["pumpkins", "lettuce", "cabbage"]
      };

      console.log(tortoiseOne.weight);

      newWeight = tortoiseOne.weight + 10;

      tortoiseOne["weight"] = newWeight;

      console.log(tortoiseOne["weight"]);
   ```

   **Console Output**

   ```console
      919
      929
   ```

{{% /notice %}}

### Add New Key/Value Pairs

After declaring and initializing an object, we can add new properties at any
time by using bracket syntax:

```js
   objectName["new-key"] = propertyValue;
```

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=table}
      let tortoiseTwo = {
          species: "Galapagos Tortoise",
          name: "Pete",
          weight: 919
      };

      console.log(tortoiseTwo);

      tortoiseTwo["age"] = 120;
      tortoiseTwo["speed"] = 'Faster than the hare.'

      console.log(tortoiseTwo);
      console.log(tortoiseTwo.age);
   ```

   **Console Output**

   ```console
      { species: 'Galapagos Tortoise', name: 'Pete', weight: 919 }
      { species: 'Galapagos Tortoise',
         name: 'Pete',
         weight: 919,
         age: 120,
         speed: 'Faster than the hare.' }
      120
   ```

{{% /notice %}}

## Check Your Understanding

All of the questions below refer to an object called `giraffe`.

```js {linenos=table}
   let giraffe = {
     species: "Reticulated Giraffe",
     name: "Cynthia",
     weight: 1500,
     age: 15,
     diet: "leaves"
   };
```

{{% notice green "Question" "rocket" %}}

   We want to add a method after the `diet` property for easily increasing Cynthia's age on her birthday.
   Which of the following is missing from our method? You can select MORE than one.

   `birthday: function () {age = age + 1;}`

   1. `return`
   1. `this`
   1. `diet`
   1. a comma

{{% /notice %}}

<!-- this and return -->

{{% notice green "Question" "rocket" %}}

   Could we use bracket syntax, dot notation, or both to access the properties of `giraffe`?

{{% /notice %}}

<!-- both -->