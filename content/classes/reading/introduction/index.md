---
title: "What are Classes?"
date: 2023-09-15T16:20:48-05:00
draft: false
weight: 1
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Recall that [objects]({{< relref "../../../objects-and-math/reading/background ">}}) are data structures that hold many
values, which consist of *properties* and *methods*.

We often need to create many objects of the same *type*. To do this in an
efficient way, we define a **class**, which allows us to set up the general
structure for an object. We can then reuse that structure to build multiple
objects. These objects all have the same set of *keys*, but the *values*
assigned to each key will vary.

Let's revisit the animal astronauts from earlier exercises to see how this
works.

## An Astronaut Object

When we create an object to hold an astronaut's data, it might look something
like:

```js {linenos=table}
let fox = {
   name: 'Fox',
   age: 7,
   mass: 12,
   catchPhrase: function(repeats) {
      let phrase = 'LaunchCode';
      for (let i = 0; i < repeats; i++) {
         phrase += ' Rocks';
      }
      return phrase;
   }
}

console.log(`${fox.name} is ${fox.age} years old and has a mass of ${fox.mass} kg.`);
console.log(`${fox.name} says, "${fox.catchPhrase(3)}."`);
```

**Console Output**

```console
Fox is 7 years old and has a mass of 12 kg.
Fox says, "LaunchCode Rocks Rocks Rocks."
```

The `fox` object contains all the data and functions for the astronaut named
`'Fox'`.

Of course, we have multiple astronauts on our team. To store data for each one,
we would need to copy the structure for `fox` multiple times and then change
the values to suit each crew member. This is inefficient and repetitive.

By letting us define our own **classes**, JavaScript provides a better way to
create multiple, similar objects.

![Visual of the relationship between classes and objects.](pictures/Classes-vs-objects.png)