---
title: "Math.max and Math.min Examples"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `Math.max`

The general syntax for this method is:

```console
   Math.max(x, y, z, ...)
```

This method finds and returns the largest value from a set of numbers (x, y, z,
...).

To find the maximum value in an array, see below.

{{% notice blue "Example" "rocket" %}}

   ```js
      console.log(Math.max(2, 3, 100.01, 0, -5.2, 100));
   ```

   **Console Output**

   ```console
      100.01
   ```

{{% /notice %}}

## `Math.min`

The general syntax for this method is:

```console
   Math.min(x, y, z, ...)
```

This method finds and returns the smallest value from a set of numbers
(x, y, z,...).

To find the minimum value in an array, see below.

{{% notice blue "Example" "rocket" %}}

   ```js
      console.log(Math.min(2, 3, 100.01, 0, -5.2, 100));
   ```

   **Console Output**

   ```console
      -5.2
   ```

{{% /notice %}}

## Max and Min of an Array

Unfortunately, the `max` and `min` methods will NOT take an array of
numbers as an argument. There are numerous workarounds. Here are TWO possible
solutions.

### Sort First

This approach uses the syntax from the sorting studio
to first order the array. The maximum (or minimum) value can then be
identified with bracket notation.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      let numbers = [-2, 3.33, -4.44, 8.88];

      let sortedArray = numbers.sort(function(a, b){return a-b});

      console.log(sortedArray);
      console.log(`Min = ${sortedArray[0]}, Max = ${sortedArray[sortedArray.length-1]}`);
   ```

   **Console Output**

   ```console
      [ -4.44, -2, 3.33, 8.88 ]
      Min = -4.44, Max = 8.88
   ```

   Alternatively, we could put the array in decreasing order:

   ```js {linenos=true}
      let numbers = [-2, 3.33, -4.44, 8.88];

      let sortedArray = numbers.sort(function(a, b){return b-a});

      console.log(sortedArray);
      console.log(`Max = ${sortedArray[0]}, Min = ${sortedArray[sortedArray.length-1]}`);
   ```

   **Console Output**

   ```console
      [ 8.88, 3.33, -2, -4.44 ]
      Max = 8.88, Min = -4.44
   ```

{{% /notice %}}

### Using Spread Syntax

An alternative to the sorting approach described above is to use the
**spread operator** (`...`), also called *spread syntax*.

In cases where a set of numbers or strings (x, y, z, etc.) is expected, an
array cannot be used as-is. The spread operator expands an array into a
comma-separated set of elements, which can be passed as arguments in a
function call. `functionName(...[x,y,z])` is identical to
`functionName(x,y,z)`.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      let numbers = [2, 3, 100.01, 0, -5.2, 100];

      let max = Math.max(...numbers);
      let min = Math.min(...numbers);

      console.log(...numbers);
      console.log(`Min = ${min}, Max = ${max}`);
   ```

   **Console Output**

   ```console
      2 3 100.01 0 -5.2 100
      Min = -5.2, Max = 100.01
   ```

{{% /notice %}}

Note the absence of brackets, `[]`, around the numbers printed by line 6.
`console.log(...numbers)` executes as
`console.log(2, 3, 100.01, 0, -5.2, 100)`, so the output is NOT an array.

{{% notice blue "Note" "rocket" %}}

   The sorting approach works in all browsers. The spread operator, while
   very convenient, is NOT compatible with Internet Explorer or older versions
   of other browsers (pre-2015). For more details on the spread operator and its
   compatibility, check the
   [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax).

{{% /notice %}}