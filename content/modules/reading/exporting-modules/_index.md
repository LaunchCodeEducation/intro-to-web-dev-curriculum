---
title: "Exporting Modules"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 4
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

We learned how to pull in useful code in the form of *modules*, but what if
we write clever code that we want to share? Fortunately, Node allows us to make
our code available for use in other programs.

First, some basic points:

1. Every Node.js file is treated as a module (also called a *package*).
1. From a file, we can export a single function or a set of functions.

## Starter Code

We will use the following code sample to practice how to **export** our work---making it available to import as a module.

```javascript
function isPalindrome(str){
    return str === str.split('').reverse().join('');
}

function evenOrOdd(num){
    if (num%2===0){
        return "Even";
    } else {
        return "Odd";
    }
}

function randomArrayElement(arr){
    let index = Math.floor(Math.random()*arr.length);
    return arr[index];
}
```

These functions are located in the `javascript-projects/modules/exporting-modules/practiceExports.js` file, and our goal is to import them into `javascript-projects/modules/exporting-modules/index.js` file.

## Exporting a Single Function

Let's start by exporting the `isPalindrome` function. At the bottom of the
`practiceExports.js` code, add the line `module.exports = isPalindrome;`.
This makes the function available to other files.

In `index.js`, we import `practiceExports.js` with a `require` statement.
`isPalindrome` gets pulled in and assigned to the new variable
`palindromeCheck`, and we can now call the function from within `index.js`.

{{% notice green "Try it!" "rocket"%}}
Add the following code to `index.js`, then click "Run".

```javascript
const palindromeCheck = require('./practiceExports.js');

console.log(typeof palindromeCheck);
console.log(palindromeCheck('that'));
console.log(palindromeCheck('radar'));
```

**Console Output**

```console
function
false
true
```
{{% /notice %}}

There are several points to make about the code and output.

1. Assigning `isPalindrome` to `module.exports` allows us to use that function in other files.
1. Even though we `require` the file `practiceExports.js`, it only assigns `isPalindrome` to the variable `palindromeCheck`. Thus, `typeof palindromeCheck` returns `function`.
1. `palindromeCheck` now behaves in the same way as `isPalindrome`, so calling `palindromeCheck('that')` evaluates to `false`, since `'that'` is not a palindrome.

## Exporting Multiple Functions

`practiceExports.js` contains three functions, and to export all of them we
use a different syntax for `module.exports`. Instead of setting up a single
function, we will create an *object*.

To export multiple functions, the syntax is:

```javascript
module.exports = {
    isPalindrome: isPalindrome,
    evenOrOdd: evenOrOdd,
    randomArrayElement: randomArrayElement
}
```

Within the `{}`, we create a series of key:value pairs. The *keys* will be the names used in `index.js` to call the functions. The *values* are the
functions themselves.

{{% notice blue Note "rocket" %}}
We do not have to make the key match the name of the function, but doing so
helps maintain consistency between files.
{{% /notice %}}

{{% notice orange Warning "rocket" %}}
You might be tempted to use three statements to export the three functions:

```javascript
module.exports = isPalindrome;
module.exports = evenOrOdd;
module.exports = randomArrayElement;
```

This will NOT work, because Node expects only ONE `module.exports` statement in a file. No error will be thrown if you use more than one, but `require('./practiceExports.js')` will only pull in the information from the LAST statement.
{{% /notice %}}

### Try It

Use the object syntax [as shown above]({{< relref "#exporting-multiple-functions" >}}) to
modify `module.exports` in `practiceExports.js`. We could include only one
or two of the functions, but for this practice let's use all of them.

Next, modify `index.js` as follows and run your code:

```javascript
const practice = require('./practiceExports.js');

console.log(typeof practice);
console.log(practice);
```

`typeof` indicates that `practice` is an object, and printing `practice`
gives us a list of its key/value pairs (e.g.
`isPalindrome: [Function: isPalindrome]`).

All of the functions from `practiceExports` are included in the `practice`
object. To call them, we use dot notation---
`practice.functionName(argument)`.

Modify `index.js` again and run your code:

```javascript
const practice = require('./practiceExports.js');
let arr = ['Hello', 'World', 123, 987, 'LC101'];

console.log(practice.isPalindrome('mom'));
console.log(practice.evenOrOdd(9));

for (i=0; i < 3; i++){
    console.log(practice.randomArrayElement(arr));
}
```

**Console Output**

```console
true
Odd
123
World
LC101
```

Success! You exported your first module.

## What If

You might be wondering, *If I have 20+ functions in a file, and I want to
export them ALL, do I really need to type 20+ key/value pairs in
module.exports?*

The quick answer is, *Yes*. `require` only pulls in items identified in
`module.exports`. The longer answer is, *Hmmm, you missed the point*.

Just like functions, we want to keep modules small and specific. Each module
should focus on a single idea and contain only a few related functions. With
this in mind, we see that `practiceExports` falls short of the goal. Even
though it is small in size, `isPalindrome`, `evenOrOdd`, and
`randomArrayElement` do not really compliment each other. They would be
better placed in different modules.

If you find yourself writing lots of functions in a single file, consider
splitting them up into smaller, more detailed modules. Doing this makes
debugging easier, organizes your work, and helps you identify which modules to
import into a new project. A module titled `cleverLC101Work` is not nearly as
helpful as one called `arraySortingMethods`.

## Check Your Understanding

{{% notice green Question "rocket" %}}
A module in Node.js is:

1. A file containing JavaScript code intended for use in other Node programs.
1. A separate block of code within a program.
1. One line of code in a program.
1. A function.
1. A file that contains documentation about functions in JavaScript.
{{% /notice %}}

{{% notice green Question "rocket" %}}
Assume you have the following at the end of a `circleStuff.js` module:

```javascript
module.exports = {
    areaOfCircle: areaOfCircle,
    circumference: circumference,
    findRadius: findRadius,
    arcLength: arcLength
}
```

Inside your project, you import `circleStuff`:

```javascript
const circleStuff = require('./circleStuff.js');
```

Which of the following is the correct way to find the circumference of a circle
from within your project?

1. `circleStuff(argument)`
1. `circleStuff.circumference(argument)`
1. `circleStuff(circumference(argument))`
1. `circumference(argument)`
{{% /notice %}}