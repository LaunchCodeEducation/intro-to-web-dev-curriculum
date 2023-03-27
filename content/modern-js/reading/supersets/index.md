---
title: "Supersets"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In addition to syntax extensions, JavaScript also has **supersets**. One such superset of JavaScript that you may see React applications written in is **TypeScript**. A superset of a language just means that a program written in TypeScript is also a valid program in JavaScript. You might wonder why not just write everything in JavaScript. TypeScript has one major difference: it is a **statically-typed** language. On the other hand, JavaScript is **dynamically-typed**. A statically typed language is a language where the type of a variable is given at the time the program is compiled. This is often achieved by adding the type of the variable to the variable declaration. In a dynamically typed language, the type of the variable is determined at runtime and is based on the value inside the variable, not the variable declaration. Statically typed languages are considered by many to be more stable and less prone to production errors, because the errors will occur in development.

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

If we try and pass a string to `distancetoMoon`, in TypeScript, the resulting error would prevent the application from building. In JavaScript, the error would be exposed at runtime.