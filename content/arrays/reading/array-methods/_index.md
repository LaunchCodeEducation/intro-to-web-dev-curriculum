---
title: "Array Methods"
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

As with strings, JavaScript provides us with useful **methods** for arrays.
These methods will either *alter* an existing array, *return* information about
the array, or *create and return* a new array.

## Common Array Methods

Here is a sample of the most frequently used array methods. More complete lists
can be found here:

1. [W3 Schools Array Methods](https://www.w3schools.com/jsref/jsref_obj_array.asp).
1. [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

To see detailed examples for a particular method, control-click
(or right-click) on its name.

### Methods That Return Information About The Array

| Method            | Syntax                           | Description                                 |
| ----------------- | -------------------------------- | ------------------------------------------- |
| includes          | `arrayName.includes(item)`       | Checks if an array contains the specified item. |
| indexOf           | `arrayName.indexOf(item)`        | Returns the index of the first occurrence of an item in the array. If the item is not in the array, -1 is returned. |

### Methods That Rearrange The Entries In The Array

| Method            | Syntax                     | Description                                 |
| ----------------- | -------------------------- | ------------------------------------------- |
| reverse           | `arrayName.reverse()`      | Reverses the order of elements in an array. |
| sort              | `arrayName.sort()`         | Arranges elements of an array in increasing order (kinda). |

### Methods That Add Or Remove Entries From An Array

| Method                    | Syntax                                | Description                                            |
| ------------------------- | ------------------------------------- | ------------------------------------------------------ |
| pop                       | `arrayName.pop()`                     | Removes and returns the LAST element in an array.     |
| push                      | `arrayName.push(item1, item2, ...)`   | Adds one or more items to the END of an array and returns the new length. |
| shift                     | `arrayName.shift()`                   | Removes and returns the FIRST element in an array.    |
| splice                    | `arrayName.splice(index, number, ...)` | Adds, removes, or replaces one or more elements anywhere in the array. |
| unshift                   | `arrayName.unshift(item1, item2, ...)` | Adds one or more items to the START of an array and

### Methods that Create New Arrays

| Method                          | Syntax                            | Description                                       |
| ------------------------------- | --------------------------------- | ------------------------------------------------- |
| [concat](concat-examples)       | `arr.concat(otherArray1, ...)`    | Combines two or more arrays into a new array.    |
| [join](join-examples)           | `arr.join('connecter')`           | Combines all elements of an array into a string. |
| [slice](slice-examples)         | `arr.slice(start index, end index)` | Copies selected entries of an array to a new array. |
| [split](split-examples)         | `stringName.split('delimiter')`    | Divides a string into smaller pieces stored in a new array. |

## Check Your Understanding

Follow the links in the table above for the `sort`, `slice`, `split` and
`join` methods. Review the content and then answer the following questions.

{{% notice green Question "rocket" %}}

What is printed by the following code?
```javascript
let charles = ['coder', 'Tech', 47, 23, 350];
charles.sort();
console.log(charles);
```

1. `[350, 23, 47, 'Tech', 'coder']`
1. `['coder', 'Tech', 23, 47, 350]`
1. `[23, 47, 350, 'coder', 'Tech']`
1. `[23, 350, 47, 'Tech', 'coder']`

<!-- Solution: [23, 350, 47, "Tech", "coder"]-->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Which statement converts the string `str = 'LaunchCode students rock!'` into the array `['LaunchCode', 'students', 'rock!']`?

a. `str.join(" ");`
b. `str.split(" ");`
c. `str.join("");`
d. `str.split("");`

<!-- Solution: None of the above, the .join method cannot be used on a string -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is printed by the following program?

```javascript
let groceryBag = ['bananas', 'apples', 'edamame', 'chips', 'cucumbers', 'milk', 'cheese'];
let selectedItems = [];

selectedItems = groceryBag.slice(2, 5).sort();
console.log(selectedItems);
```

1. `['chips', 'cucumbers', 'edamame']`
1. `['chips', 'cucumbers', 'edamame', 'milk']`
1. `['cheese', 'chips', 'cucumbers']`
1. `['cheese', 'chips', 'cucumbers', 'edamame']`

<!-- Solution: Option 1: chips, cucumbers, edamame] -->
{{% /notice %}}