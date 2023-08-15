---
title: "Exercises: Functions"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

To solve problems with code, you need to be able to break large
problems into small ones. Usually, these smaller problems will take the form of
functions that are used to solve the larger problem. Therefore, to solve problems with code, 
you need to be skilled at writing functions. And to master
functions, you need to write a *lot* of them.

These exercises ask you to write many relatively small functions, which
combine to form larger, more complicated ones.

At the end, you will be able to create strings of shapes, like this nifty
diamond:

```console
     #
    ###
   #####
  #######
 #########
 #########
  #######
   #####
    ###
     #
```

There is no starter code for these exercises, so create a new JavaScript file within your `javascript-projects/functions` directory to get started.

## Rectangles

### `makeLine(size)` function

Write a function `makeLine(size)` that returns a line with exactly `size` hashes.

```javascript
console.log(makeLine(5));
```

**Console Output**

```console
 #####
```

{{% expand "Check Your Solution" %}}
```javascript
function makeLine(size) {
  let line = '';
  for (let i = 0; i < size; i++) {
    line += '#';
  }
  return line;
}
```
{{% /expand %}}

### `makeSquare(size)` function

Write a function called `makeSquare(size)` that returns a `size` by `size` string of hashes. The function should NOT print each row of the square. Instead, it must return a single string that contains the entire shape.

{{% notice green Tip "rocket" %}}
1. Call your `makeLine` function to create each row of the square.
1. The newline character, `\n`, will be helpful to you.
1. Do NOT include a newline character at the end of your string.
{{% /notice %}}
   
```javascript
console.log(makeSquare(5));
```

**Console Output**

```console
 #####
 #####
 #####
 #####
 #####
```

{{% notice orange Warning "rocket" %}}
For each of the shape exercises, do not include a newline character at the very end of your string. While the final `\n` might not be
noticeable for the simpler shapes, including it will make life harder for you toward the end of the exercises.
{{% /notice %}}

### `makeRectangle(width, height)` function

Write a function `makeRectangle(width, height)` that returns a rectangle with the given width and height. Use your `makeLine` function to do this.

```javascript
console.log(makeRectangle(5, 3));
```

**Console Output**

```console
 #####
 #####
 #####
```

{{% expand "Check Your Solution" %}}
```javascript
function makeRectangle(width, height) {
  let rectangle = '';
  for (let i = 0; i < height; i++) {
    rectangle += (makeLine(width) + '\n');
  }
  return rectangle.slice(0, -1);
}
```
{{% /expand %}} 

Now, go back and rewrite `makeSquare` to use `makeRectangle`.

## Triangles

### `makeDownwardStairs(height)` function

Write a function `makeDownwardStairs(height)` that prints the staircase pattern shown below, with the given height. Use your `makeLine` function to do this.

```javascript
console.log(makeDownwardStairs(5));
```

**Console Output**

```console
 #
 ##
 ###
 ####
 #####
```

{{% expand "Check Your Solution" %}}
```javascript
function makeDownwardStairs(height) {
  let stairs = '';
  for (let i = 0; i < height; i++) {
    stairs += (makeLine(i+1) + '\n');
  }
  return stairs.slice(0, -1);
}
```
{{% /expand %}}

### `makeSpaceLine(numSpaces, numChars)` function

Write a function `makeSpaceLine(numSpaces, numChars)` that returns a line with exactly the specified number of spaces, followed by the specified number of hashes, followed again by `numSpaces` more spaces.

```javascript
console.log(makeSpaceLine(3, 5));
```

**Console Output**

```console
___#####___
```

{{% notice blue Note "rocket" %}}
We have inserted underscores to represent spaces, so they are visible in the output. Don't do this in your code.
{{% /notice %}}

### `makeIsoscelesTriangle(height)` function

Write a function `makeIsoscelesTriangle(height)` that returns a triangle of the given height.

```javascript
console.log(makeIsoscelesTriangle(5));
```

**Console Output**

```console
     #
    ###
   #####
  #######
 #########
```

{{% notice green Tip "rocket" %}}
Consider the top line of the triangle to be level 0, the next to be line 1, and so on. Then line `i` is a space-line with `height - i - 1` spaces and `2 * i + 1` hashes.
{{% /notice %}}

{{% expand "Check Your Solution" %}}
```javascript
function makeIsoscelesTriangle(height) {
  let triangle = '';
  for (let i = 0; i < height; i++) {
    triangle += (makeSpaceLine(height - i - 1, 2*i + 1) + '\n');
  }
  return triangle.slice(0, -1);
}
```
{{% /expand %}}

## Diamonds

### `makeDiamond(height)` function

Write a function `makeDiamond(height)` that returns a diamond where the triangle formed by the *top* portion has the given height.

```javascript
console.log(makeDiamond(5));
```

**Console Output**

```console
     #
    ###
   #####
  #######
 #########
 #########
  #######
   #####
    ###
     #
```

{{% notice green Tip "rocket" %}}
Consider what happens if you create a triangle and reverse it using [our reverse function]({{< relref "../reading/composing-functions/_index.md#the-reverse-function" >}}).
{{% /notice %}}

## Bonus Mission

Refactor your functions so that they take a single character as a parameter, and draw the shapes with that character instead of always using `'#'`. Make the new parameter optional, with default value `'#'`.