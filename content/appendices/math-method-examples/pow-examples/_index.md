---
title: "Math.pow and Math.sqrt Examples"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `Math.pow`

The general syntax for this method is:

```console
   Math.pow(x, y)
```

This method calculates and returns the value of x raised to the power of y
(x :sup:`y`), and it is identical to the `x**y` operation. The *pow* name
refers to the operation *to the power of*.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      console.log(3**4);
      console.log(Math.pow(3,4));
      //3 raised to the power of 4 = 3*3*3*3
   ```

   **Console Output**

   ```console
      81
      81
   ```

{{% /notice %}}

## `Math.sqrt`

The general syntax for this method is:

```console
   Math.sqrt(number)
```

This method calculates and returns the square root of `number`, and it is a
shortcut for using the fraction 1/2 in the `pow` method.

Numerical strings can also be evaluated, but should be avoided as a best
practice.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      console.log(Math.sqrt(81));
      console.log(Math.pow(81,1/2));

      console.log(Math.sqrt(111));
      console.log(Math.sqrt("36"));
   ```

   **Console Output**

   ```console
      9
      9
      10.535653752852738
      6
   ```

{{% /notice %}}

`Math.sqrt` also works on arrays, but must be combined with the
map array method. The syntax for this is:

```console
   arrayName.map(Math.sqrt)
```

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      let numbers = [2, 16, 100, 121];

      console.log(numbers.map(Math.sqrt));
   ```

   **Console Output**

   ```console
      [ 1.4142135623730951, 4, 10, 11 ]
   ```

{{% /notice %}}