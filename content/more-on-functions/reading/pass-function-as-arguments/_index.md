---
title: "Passing Functions as Arguments"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

*Functions are data*, and therefore can be passed around just like other values. This means a function can be *passed to another function* as an argument. This allows the *function being called* to use the *function argument* to carry out its action. This turns out to be extremely useful. 

Examples best illustrate this technique, so let's look at a couple now.

## Example: `setTimeout`

The built-in function `setTimeout` allows a programmer to pass a function, specifying that it should be called at a later point in time. Its basic syntax is:

```console
setTimeout(func, delayInMilliseconds);
```

{{% notice blue Example "rocket" %}}
Suppose we want to log a message with a 5 second delay. Since five seconds is 5000 milliseconds (1 second = 1000 milliseconds), we can do so like this:

```javascript
function printMessage() {
    console.log("The future is now!");
}

setTimeout(printMessage, 5000);
```

**Console Output**

```console
"The future is now!"
```
{{% /notice %}}

{{% notice blue "Try It!" "rocket" %}}
Is the call to `printMessage` actually delayed? Don't just take our word for it, try this yourself. Play with our example to change the delay.
{{% /notice %}}

The function `printMessage` is *passed* to `setTimeout` the same as any other argument. 

A common twist often used by JavaScript programmers is to use an *anonymous* function as an argument.

{{% notice blue Example "rocket" %}}
This program has the same behavior as the one above. Instead of creating a named function and passing it to `setTimeout`, it creates an anonymous function within `setTimeout`'s argument list.

```javascript
setTimeout(function () {
    console.log("The future is now!");
}, 5000);
```

Examples like this look odd at first. However, they become easier to read over time. Additionally, code that passes anonymous functions is ubiquitous in JavaScript. 
{{% /notice %}}

## Example: The Array Method `map`

The array method `map` allows for every element in an array to be *mapped*
or *translated*, using a given function. Here's how to use it:

```javascript
let mappedArray = someArray.map(functionName);
```

When the `map` method executes, the following actions occur:

1. The first element in `someArray` is passed into `functionName` as an argument.
1. `functionName` executes and returns a new value.
1. The return value is added to `mappedArray`.
1. Steps 1 - 3 repeat for each element in `someArray`.

When complete, `mappedArray`, contains each of the individual return values
from the mapping function, `functionName`.

{{% notice blue Example "rocket" %}}
```javascript
let nums = [3.14, 42, 4811];

let timesTwo = function (n) {
    return n*2;
};

let doubled = nums.map(timesTwo);

console.log(nums);
console.log(doubled);
```

**Console Output**

```console
[3.14, 42, 4811]
[ 6.28, 84, 9622 ]
```
{{% /notice %}}

Notice that `map` does *not* alter the original array.

When using `map`, many programmers will define the mapping function anonymously in the same statement as the method call `map`.

{{% notice blue Example "rocket" %}}
This program has the same output as the one immediately above. The mapping function is defined anonymously within the call to `map`.

```javascript
let nums = [3.14, 42, 4811];

let doubled = nums.map(function (n) {
    return n*2;
});

console.log(doubled);
```

**Console Output**

```console
[ 6.28, 84, 9622 ]
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Similar to the `map` example above, finish the program below to halve each number in an array.

```javascript
let nums = [3.14, 42, 4811];

// TODO: Write a mapping function
// and pass it to .map()
let halved = nums.map();

console.log(halved);
```
{{% /notice %}}

{{% notice green Question "rocket" %}}
Use the ``map`` method to map an array of strings. For each name in the array, map it to the first initial.

```javascript
let names = ["Chris", "Jim", "Sally", "Blake", "Paul", "John", "Courtney", "Carly"];

// TODO: Write a mapping function
// and pass it to .map()
let firstInitials = names.map();

console.log(firstInitials);
```
{{% /notice %}}