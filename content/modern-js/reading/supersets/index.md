---
title: "Supersets"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In addition to syntax extensions, JavaScript also has **supersets**. A superset of a language just means that a program written in TypeScript is also a valid program in JavaScript. Unlike a syntax extension, a superset is its own programming language with its own syntax rules. Some React applications are written in **TypeScript**, which is a superset of JavaScript. Since TypeScript programs are also valid as JavaScript programs, you might be wondering why choose to write something in TypeScript. While it is true that TypeScript programs are valid as JavaScript programs, TypeScript has one major difference: it is a **statically typed** language. On the other hand, JavaScript is **dynamically typed**. A statically typed language is a language where the type of a variable is given at the time the program is compiled. This is often achieved by adding the type of the variable to the variable declaration. In a dynamically typed language, the type of the variable is determined at runtime and is based on the value inside the variable, not the variable declaration. Statically typed languages are considered by many to be more stable and less prone to production errors, because the errors will occur in development.

## Variable Declaration

To declare a variable in TypeScript, we have to specify the type.

```ts
   let variableName : variableType = value;
```

Let's take a look at a prior example:

```js {linenos = table}
   // In JavaScript, we have:

let spaceShuttleName = "Determination";
let shuttleSpeed = 17500;
let distancetoMars = 225000000;
let distancetoMoon = 384400;
let milesperKilometer = 0.621;
```

The same variable declarations in TypeScript would be:

```ts {linenos = table}
   // The same declarations in TypeScript would be:

let spaceShuttleName: string = "Determination";
let shuttleSpeed: number = 17500;
let distancetoMars: number = 225000000;
let distancetoMoon: number = 384400;
let milesperKilometer: number = 0.621;
```

Now let's write some broken code that will update the value of `distancetoMoon`.

```js
   distancetoMoon = "384401";
```

In both JavaScript and TypeScript, the above line of code will result in an error because `distancetoMoon` was declared above in both languages as a number. However, in TypeScript, the resulting error would prevent the application from building, providing us developers with a safety net. In JavaScript, the error would be exposed at runtime, which makes it harder for us to track the broken logic.

{{% notice blue "Note" "rocket" %}}
   Another reason to use TypeScript is that it includes several features that JavaScript doesn't. Developers can use interfaces, abstract classes, and function overloading when working with TypeScript which we will learn more about in Unit 2. 
{{% /notice %}}

## TypeScript Collections

Arrays in TypeScript must contain values of the same type. When declaring an array, the type needs to be declared.

```ts
let arrayName: number[] = [10,9,8];
```

What if the array needs to hold values of different types?

Now, we need a **tuple**. A tuple is a special structure in TypeScript that can hold as many values as needed of different types.

```ts
let tupleName: [number, string, number];
tupleName = [10, "9", 8];
```

This is just a short introduction to TypeScript to expose you to supersets and one of the most famous ones in the JavaScript landscape. Not only can React applications be writting in TypeScript, but Angular, a popular front-end framework, is written in TypeScript. In addition to its popularity, learning a bit more about TypeScript can help you make the transition to Unit 2, where the back-end development is done with a statically typed language.

## Check Your Understanding

{{% notice green "Question" "rocket" %}}

   TypeScript is __________ typed and JavaScript is __________ typed.

   1. dynamically, dynamically
   1. statically, statically
   1. statically, dynamically
   1. dynamically, statically

{{% /notice %}}

<!-- statically, dynamically -->

{{% notice green "Question" "rocket" %}}

   The correct TypeScript declaration of the variable, `astronautName`, that holds the value, `"Sally Ride"`, is:

   1. `let astronautName = "Sally Ride";`
   1. `let astronautName = string: "Sally Ride";`
   1. `let astronautName: string = "Sally Ride";`
   1. `string astronautName = "Sally Ride";`

{{% /notice %}}

<!-- let astronautName: string = "Sally Ride"; -->

{{% notice green "Question" "rocket" %}}

   What is the appropriate collection type for this collection, `["Costco", 4.97, 3]`?

   1. Array
   1. List
   1. Tuple
   1. Dictionary

{{% /notice %}}

<!-- tuple -->