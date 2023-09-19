---
title: "Primitive Data Types"
date: 2023-09-14T11:34:32-05:00
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

In JavaScript, data types can fall into one of two categories: primitive or object types.
A primitive data type specifies the size and type of variable values, and it has no additional methods.
Using primitive data types, we can build more complex data structures or object data types.

While object types such as objects and arrays are mutable, primitive data types are immutable.
Immutable data types are data types that cannot be changed once the value has been created.

Primitive data types include:

1. Strings
1. Numbers
1. Booleans
1. `undefined`
1. `null`

## `undefined`

`undefined` is a primitive data type in JavaScript that is assigned to declared variables which have *not* been initialized.

```js
   let x;
   console.log(x)
```

Console Output

```console
   undefined
```

## `null`

`null` is similar to `undefined` in that it represents an unknown value, however, it is assigned to values that the programmer wishes to keep empty.

```js
   let x = null;
   console.log(x);
```

Console Output

```console
   null
```

## Example

Let's say that we are still working for the zoo. We have objects created for animals like so:

```js {linenos=table}
   let giraffe = {
      species: "Reticulated Giraffe",
      name: "Cynthia",
      weight: 1500,
      age: 15,
      diet: "leaves"
   };
```

Now, a new giraffe is coming to the zoo. We may want to initialize an object for the giraffe, but hold off on storing information in the `weight` property until the giraffe arrives.
In this case, we could initialize the `weight` property like so:

```js {linenos=table}
   let giraffeTwo = {
      species: "Reticulated Giraffe",
      name: "Alicia",
      weight: null,
      age: 10,
      diet: "leaves"
   };
```

This way, our object is properly initialized with all of the information we would need and we can update the `weight` property later when we have accurate information.

## Check Your Understanding

{{% notice green "Question" "rocket" %}}

   Which of the following are primitive data types? Mark ALL that apply.

   1. arrays
   1. Strings
   1. objects
   1. `null`

{{% /notice %}}

<!-- strings and null -->

{{% notice green "Question" "rocket" %}}

   Consider the following code block:

   ```js
      let x;

      console.log(x);
   ```

   `x` is of what data type?

   1. `null`
   1. `undefined`
   1. `NaN` 
   1. number

{{% /notice %}}

<!-- undefined -->
