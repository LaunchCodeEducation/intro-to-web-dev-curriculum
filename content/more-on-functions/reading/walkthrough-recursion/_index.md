---
title: "Recursion Walkthrough: The Base Case"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 7
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

To ease into the concept of recursion, let's start with a loop task.

In the Arrays chapter, we examined [the join method]({{< relref "../../../appendices/array-method-examples/join-examples/_index.md" >}}),
which combines the elements of an array into a single string. If we have
`arr = ['L', 'C', '1', '0', '1']`, then `arr.join('')` returns the string
`'LC101'`.

We can reproduce this action with either a `for` or a `while` loop.

## Joining Array Elements With a Loop

Examine the code samples below:

{{% notice blue Example "rocket" %}}
- Use a `for` loop to iterate through the array and add each entry into the `newString` variable.

```javascript
let arr = ['L', 'C', '1', '0', '1'];
let newString = '';

for (i = 0; i < arr.length; i++){
    newString = newString + arr[i];
}

console.log(newString);
console.log(arr);
```

**Console Output**

```console
'LC101'
['L', 'C', '1', '0', '1']
```
{{% /notice %}}

{{% notice blue Example "rocket" %}}
Use a `while` loop to add the first element in the array to `newString`, then remove that element from the array.

```javascript
let arr = ['L', 'C', '1', '0', '1'];
let newString = '';

while (arr.length > 0){
    newString += arr[0];
    arr.shift();
}
console.log(newString);
console.log(arr);
```

**Console Output**

```console
'LC101'
[ ]
```
{{% /notice %}}

Inside each loop, the code simply adds two strings together---whatever is
stored in `newString` plus one element from the array. In the `for` loop,
the element is the next item in the sequence of entries.  In the `while`
loop, the element is always the first entry from whatever remains in the array.

OK, the loops join the array elements together. Now let's see how to
accomplish the same task without a `for` or `while` statement.

## Bring In Recursion Concepts

First, state the problem to solve: *Combine the elements from an array into a
string*.

Second, split the problem into small, identical steps: Looking at the loops
above, the "identical step" is just adding two strings together - `newString`
and the next entry in the array.

Third, build a function to accomplish the small steps: Let's call the function
`combineEntries`, and we will set an array as the parameter.

```javascript
function combineEntries(arrayName){
    //TODO: Add code here
}
```

We want `combineEntries` to repeat over and over again until the task is
complete.

How do we make this happen without using `for` or `while`?

## Identifying the Base Case

`for` and `while` loops end when a particular condition evaluates to `false`. In the examples above, these conditions are `i < arr.length` and `arr.length > 0`, respectively.

With recursion, we do not know how many times `combineEntries` must be
called. To make sure the code stops at the proper time, we need to identify a
condition that ends the process. This is called the **base case**, and it
represents the simplest possible task for our function.

`if` the base case is `true`, the recursion ends and the task is complete.
`if` the base case is `false`, the function calls itself again.

We check for the base case like this:

```javascript
function combineEntries(arrayName){
    if (baseCase is true){
        //solve last small step
        //end recursion
    } else {
        //call combineEntries again
    }
}
```

For the joining task, the *base case* occurs when we pass in a one-element array (e.g. `[ 'L' ]`). With no other elements to join together, the function
just needs to return `'L'`.

Let's update `combineEntries` to check if the array contains only one item.

```javascript
function combineEntries(arrayName){
    if (arrayName.length <= 1){
        return arrayName[0];
    } else {
        //call combineEntries again
    }
}
```

`arrayName.length <= 1` sets up the condition for ending the recursion process. If it is `true`, the single entry gets returned, and the function
stops. Otherwise, `combineEntries` gets called again.

{{% notice blue Note "rocket" %}}
We define our base case as `arrayName.length <= 1` rather than `arrayName.length === 1` just in case an empty array `[]` gets passed to the function.
{{% /notice %}}

## The Case for the Base

What if we accidentally typed `arrayName.length === 2` as the condition for
ending the recursion? If so, it evaluates to `true` for the array
`['0', '1']`, and the function returns `'0'`. However, this leaves the
element `'1'` in the array instead of adding it to the string. By mistyping
the condition, we ended the recursion process too soon.

Similarly, if we used `arrayName[0] === 'Rutabaga'` as the condition, then
any array that does NOT contain the string `'Rutabaga'` would never match the
base case. In situations where the base case cannot be reached, the recursion
process either throws an error, or it continues without end---an infinite loop.

Correctly identifying and checking for the base case is *critical* to building
a working recursive process.

## Check Your Understanding

{{% notice green Question "rocket" %}}
We can use recursion to remove all of the 'i' entries from the array
`['One', 'i', 'c', 'X', 'i', 'i', 54]`.

Consider the code sample below, which declares the `removeI` function.

```javascript
function removeI(arr) {
    if (baseCase is true){
    //return final array
    //end recursion
    } else {
    //remove one 'i' entry from array
    //call removeI function again
    }
};
```

Which TWO of the following work as a base case for the function? Feel free to
test the options in VScode to check your thinking.

1. `!arr.includes('i')`
1. `arr.includes('i')`
1. `arr.indexOf('i')===-1`
1. `arr.indexOf('i') !== -1`
{{% /notice %}}

{{% notice green Question "rocket" %}}
The **factorial** of a number (n!) is the product of a positive, whole number and
all the positive integers below it.

For example, four factorial is 4! = 4\*3\*2\*1 = 24, and 5! = 5\*4\*3\*2\*1 =
120.

Consider the code sample below, which declares the `factorial` function.

```javascript
function factorial(integer) {
    if (baseCase is true){
    //solve last step
    //end recursion
    } else {
    //call factorial function again
    }
};
```

Which of the following should be used as base case for the function?

1. `integer === 1`
1. `integer < 1`
1. `integer === 0`
1. `integer < 0`
{{% /notice %}}