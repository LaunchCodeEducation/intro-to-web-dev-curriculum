---
title: "Math.ceil, floor, and trunc Examples"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `Math.ceil`

The general syntax for this method is:

```console
   Math.ceil(number)
```

This method rounds a decimal value UP to the next integer (hence the
*ceiling* reference in the name). Integer values remain the same.

`ceil` also operates on arrays.

Numerical strings can also be evaluated, but should be avoided as a best
practice.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      console.log(Math.ceil(8.88));

      console.log(Math.ceil(8.1));

      console.log(Math.ceil(-3.9));

      console.log(Math.ceil(5));
   ```

   **Console Output**

   ```console
      9
      9
      -3
      5
   ```

{{% /notice %}}

## `Math.floor`

The general syntax for this method is:

```console
   Math.floor(number)
```

This method is the opposite of `Math.ceil`. It rounds a decimal value DOWN to
the previous integer. Integer values remain the same.

`floor` also operates on arrays.

Numerical strings can also be evaluated, but should be avoided as a best
practice.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      console.log(Math.floor(8.88));

      console.log(Math.floor(8.1));

      console.log(Math.floor(-3.9));

      console.log(Math.floor(5));
   ```

   **Console Output**

   ```console
      8
      8
      -4
      5
   ```

{{% /notice %}}

## `Math.trunc`

The general syntax for this method is:

```console
   Math.trunc(number)
```

This method removes any decimals and returns only the integer part of `number`.

`trunc` also operates on arrays.

Numerical strings can also be evaluated, but should be avoided as a best
practice.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      console.log(Math.trunc(8.88));

      console.log(Math.trunc(10.000111));
   ```

   **Console Output**

   ```console
      8
      10
   ```

{{% /notice %}}

{{% notice blue "Note" "rocket" %}}

   At first glance, `Math.floor` and `Math.trunc` appear to do exactly the
   same thing. However, a closer look shows that the two methods treat negative numbers
   differently.

   ```js {linenos=true}
      console.log(Math.floor(-15.88));

      console.log(Math.trunc(-15.88));
   ```

   **Console Output**

   ```console
      -16
      -15
   ```

{{% /notice %}}

## Combine with `map`

When combined with the map array method, `ceil`, `floor`, and `trunc`
will operate on each entry in an array. The syntax for this is:

```console
   arrayName.map(Math.method)
```

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      let numbers = [-2, 3.33, -4.44, 8.88];

      console.log(numbers.map(Math.ceil));
      console.log(numbers.map(Math.floor));
      console.log(numbers.map(Math.trunc));
   ```

   **Console Output**

   ```console
      [ -2, 4, -4, 9 ]
      [ -2, 3, -5, 8 ]
      [ -2, 3, -4, 8 ]
   ```

{{% /notice %}}