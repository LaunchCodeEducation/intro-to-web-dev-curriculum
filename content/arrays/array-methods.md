# Array Methods

::: index
single: array; methods
:::

As with strings, JavaScript provides us with useful **methods** for
arrays. These methods will either *alter* an existing array, *return*
information about the array, or *create and return* a new array.

## Common Array Methods

Here is a sample of the most frequently used array methods. More
complete lists can be found here:

1.  [W3 Schools Array
    Methods](https://www.w3schools.com/jsref/jsref_obj_array.asp)
2.  [MDN Web
    Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

To see detailed examples for a particular method, control-click (or
right-click) on its name.

  Method                                                         Syntax                       Description
  -------------------------------------------------------------- ---------------------------- ---------------------------------------------------------------------------------------------------------------------
  `includes <includes-examples>`{.interpreted-text role="ref"}   `arrayName.includes(item)`   Checks if an array contains the specified item.
  `indexOf <indexOf-examples>`{.interpreted-text role="ref"}     `arrayName.indexOf(item)`    Returns the index of the FIRST occurrence of an item in the array. If the item is not in the array, -1 is returned.

  : Methods That Return Information About The Array

  Method                                                      Syntax                  Description
  ----------------------------------------------------------- ----------------------- ------------------------------------------------------------------
  `reverse <reverse-example>`{.interpreted-text role="ref"}   `arrayName.reverse()`   Reverses the order of the elements in an array.
  `sort <sort-examples>`{.interpreted-text role="ref"}        `arrayName.sort()`      Arranges the elements of an array into increasing order (kinda).

  : Methods That Rearrange The Entries In The Array

  Method                                                               Syntax                                                 Description
  -------------------------------------------------------------------- ------------------------------------------------------ -----------------------------------------------------------------------------
  `pop <pop>`{.interpreted-text role="ref"}                            `arrayName.pop()`                                      Removes and returns the LAST element in an array.
  `push <push-and-pop-examples>`{.interpreted-text role="ref"}         `arrayName.push(item1, item2, ...)`                    Adds one or more items to the END of an array and returns the new length.
  `shift <shift-and-unshift-examples>`{.interpreted-text role="ref"}   `arrayName.shift()`                                    Removes and returns the FIRST element in an array.
  `splice <splice-examples>`{.interpreted-text role="ref"}             `arrayName.splice(index, number, item1, item2, ...)`   Adds, removes or replaces one or more elements anywhere in the array.
  `unshift <unshift>`{.interpreted-text role="ref"}                    `arrayName.unshift(item1, item2, ...)`                 Adds one or more items to the START of an array and returns the new length.

  : Methods That Add Or Remove Entries From An Array

  Method                                                     Syntax                                        Description
  ---------------------------------------------------------- --------------------------------------------- ------------------------------------------------------------------------
  `concat <concat-examples>`{.interpreted-text role="ref"}   `arr.concat(otherArray1, otherArray2, ...)`   Combines two or more arrays and returns the result as a new array.
  `join <join-examples>`{.interpreted-text role="ref"}       `arr.join('connecter')`                       Combines all the elements of an array into a string.
  `slice <slice-examples>`{.interpreted-text role="ref"}     `arr.slice(start index, end index)`           Copies selected entries of an array into a new array.
  `split <split-examples>`{.interpreted-text role="ref"}     `stringName.split('delimiter')`               Divides a string into smaller pieces, which are stored in a new array.

  : Methods That Create New Arrays

## Check Your Understanding

Follow the links in the table above for the `sort`, `slice`, `split` and
`join` methods. Review the content and then answer the following
questions.

::: admonition
Question

What is printed by the following code?

``` {.js linenos=""}
let charles = ['coder', 'Tech', 47, 23, 350];
charles.sort();
console.log(charles);
```

a.  `[350, 23, 47, 'Tech', 'coder']`
b.  `['coder', 'Tech', 23, 47, 350]`
c.  `[23, 47, 350, 'coder', 'Tech']`
d.  `[23, 350, 47, 'Tech', 'coder']`
:::

::: admonition
Question

Which statement converts the string `str = 'LaunchCode students rock!'`
into the array `['LaunchCode', 'students', 'rock!']`?

a.  `str.join(" ");`
b.  `str.split(" ");`
c.  `str.join("");`
d.  `str.split("");`
:::

::: admonition
Question

What is printed by the following program?

``` {.js linenos=""}
let groceryBag = ['bananas', 'apples', 'edamame', 'chips', 'cucumbers', 'milk', 'cheese'];
let selectedItems = [];

selectedItems = groceryBag.slice(2, 5).sort();
console.log(selectedItems);
```

a.  `['chips', 'cucumbers', 'edamame']`
b.  `['chips', 'cucumbers', 'edamame', 'milk']`
c.  `['cheese', 'chips', 'cucumbers']`
d.  `['cheese', 'chips', 'cucumbers', 'edamame']`
:::
