---
title: "Exercises: Arrays"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

OK, rookie. It's time to train you on how to modify the shuttle's cargo
manifest. The following actions will teach you how to add, remove, modify and
rearrange our records for the items stored in our hold.

## Part 1

Create an array called `practiceFile` with the following entry: 273.15. Use the `push` method to add the following elements to the array. Add items 1 & 2 one at a time, then use a single `push` to add the items within section 3. Print the array after each step to confirm the changes.

1. 42
1. "hello"
1. `false`, -4.6, "87"

*Congratulations, rookie. You can now add items to an array.*

{{% expand "Check Your Solution" %}}
```javascript
let practiceFile = [273.15];
```

### Section 1:
```javascript
practiceFile.push(42);
console.log(practiceFile);
```
### Section 3:
```javascript
practiceFile.push(false, -4.6, "87");
console.log(practiceFile);
```
{{% /expand %}}

## Part 2

`push`, `pop`, `shift` and `unshift` are used to add/remove elements from the beginning/end of an array. **Bracket notation** can be used to modify any element within an array. Starting with the `cargoHold` array `['oxygen tanks', 'space suits', 'parrot', 'instruction manual',
'meal packs', 'slinky', 'security blanket']`

write statements to do the following:

1. Use bracket notation to replace `'slinky'` in the array with `'space
tether'`. Print the array to confirm the change.
1. Remove the last item from the array with `pop`. Print the element
removed and the updated array.
1. Remove the first item from the array with `shift`. Print the element
removed and the updated array.
1. Unlike `pop` and `shift`, `push` and `unshift` require arguments
inside the `()`. Add the items 1138 and '20 meters' to the array -
the number at the start and the string at the end. Print the updated
array to confirm the changes.
1. Use a template literal to print the final array and its length.

*Status check, rookie. Which array methods ADD items, and where are the new
entries placed? Which methods REMOVE items, and where do the entries come
from? Which methods require entries inside the `()`?*

{{% expand "Check Your Solution" %}}
```javascript
let cargoHold = ['oxygen tanks', 'space suits', 'parrot', 'instruction manual', 'meal packs', 'slinky', 'security blanket'];
```

### Section 1:
```javascript
cargoHold[5] = 'space tether';
console.log(cargoHold);
```

### Section 3:
```javascript
console.log(cargoHold.shift());
console.log(cargoHold);
```

### Section 5:
```javascript
console.log(`The array ${cargoHold} has a length of ${cargoHold.length}.`);
```
{{% /expand %}}

## Part 3

The `splice` method can be used to either add or remove items from an
array. It can also accomplish both tasks at the same time. Review the
:ref:`splice appendix <splice-examples>` if you need a syntax reminder. Use
`splice` to make the following changes to the final `cargoHold` array
from exercise 2. Be sure to print the array after each step to confirm your
updates.

1. Insert the string `'keys'` at index 3 without replacing any other
entries.
1. Remove 'instruction manual' from the array. (Hint: `indexOf` is helpful
to avoid manually counting an index).
1. Replace the elements at indexes 2 - 4 with the items `'cat'`,
`'fob'`, and `'string cheese'`.

{{% expand "Check Your Solution" %}}
### Section 1:
```javascript
cargoHold.splice(3,0,'keys');
console.log(cargoHold);
```

### Section 3:
```javascript
cargoHold.splice(2,3,'cat','fob','string cheese');
console.log(cargoHold);
```
{{% /expand %}}

*Well done, cadet. Now let's look at some finer details about array methods.
We've got to keep our paperwork straight, so you need to know when your
actions change the original records.*

## Part 4

Some methods---like `splice` and `push`---alter the original array,
while others do not. Use the the following arrays:

```javascript
holdCabinet1 ['duct tape', 'gum', 3.14, false, 6.022e23]
```

and

```javascript
holdCabinet2 ['orange drink', 'nerf toys', 'camera', 42, 'parsnip']
```

to explore the following methods: `concat`, `slice`, `reverse`, `sort`. Refer back to the chapter if you need to review the proper syntax for any of these methods.

1. Print the result of using `concat` on the two arrays. Does `concat`
alter the original arrays? Verify this by printing `holdCabinet1`
after using the method.
1. Print a `slice` of two elements from each array. Does `slice` alter the
original arrays?
1. `reverse` the first array, and `sort` the second. What is the difference
between these two methods? Do the methods alter the original arrays?

*Good progress, cadet. Here are two more methods for you to examine.*

{{% expand "Check Your Solution" %}}
### Section 1:
```javascript
console.log(holdCabinet1.concat(holdCabinet2));
console.log(holdCabinet1);
```

### Section 3:
```javascript
holdCabinet1.reverse();
holdCabinet2.sort();
console.log(holdCabinet1);
console.log(holdCabinet2);
```
{{% /expand %}}

## Part 5

The `split` method converts a string into an array, while the `join`
method does the opposite.

1. Try it! Given the string `str = 'In space, no one can hear you code.'`,
see what happens when you print `str.split()` vs. `str.split('e')`
vs. `str.split(' ')` vs. `str.split('')`. What is the purpose of the
parameter inside the `()`?
1. Given the array `arr = ['B', 'n', 'n', 5]`, see what happens when
you print `arr.join()` vs. `arr.join('a')` vs. `arr.join(' ')` vs.
`arr.join('')`. What is the purpose of the parameter inside the `()`?
1. Do `split` or `join` change the original string/array?
1. The benefit, cadet, is that we can take a string with **delimiters**
(like commas) and convert it into a modifiable array. *Try it!*
Alphabetize these hold contents: "water,space suits,food,plasma
sword,batteries", and then combine them into a new string.

*Nicely done, astronaut. Now it's time to bring you fully up to speed.*

{{% expand "Check Your Solution" %}}
### Section 1:
```javascript
console.log(str.split());
console.log(str.split('e'));
console.log(str.split(' '));
console.log(str.split(''));
```

### Section 3:
```javascript
console.log(cargoHold.split(',').sort().join(','));
```
{{% /expand %}}

## Part 6

Arrays can hold different data types, even other arrays! A
**multi-dimensional array** is one with entries that are themselves arrays.

1. Define and initialize the following arrays, which hold the name, chemical
symbol and mass for different elements:

- `element1 = ['hydrogen', 'H', 1.008]`
- `element2 = ['helium', 'He', 4.003]`
- `element26 = ['iron', 'Fe', 55.85]`

2. Define the array `table`, and use `push(arrayName)` to add each of
the element arrays to it. Print `table` to see its structure.
3. Use bracket notation to examine the difference between printing
`table[1]` and `table[1][1]`. Don't just nod your head! I want to
HEAR you describe this difference. Go ahead, talk to your screen.
4. Using bracket notation and the `table` array, print the mass of
element1, the name for element 2 and the symbol for element26.
5. `table` is an example of a *2-dimensional array*. The first "level"
contains the element arrays, and the second level holds the
name/symbol/mass values. **Experiment!** Create a 3-dimensional array and
print out one entry from each level in the array.

{{% expand "Check Your Solution" %}}
### Section 1:
```javascript
let element1 = ['hydrogen', 'H', 1.008];
let element2 = ['helium', 'He', 4.003];
let element26 = ['iron', 'Fe', 55.85];
```

### Section 3:
```javascript
console.log(table[1], table[1][1]);
```
{{% /expand %}}

*Excellent work, records keeper. Welcome aboard.*

