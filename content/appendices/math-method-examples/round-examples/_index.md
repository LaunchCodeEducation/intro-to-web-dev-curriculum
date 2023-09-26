---
title: "Math.round Examples"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 5
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

The general syntax for this method is:

```console
   Math.round(number)
```

This method returns `number` rounded to the nearest integer value.

Numerical strings can also be evaluated, but should be avoided as a best
practice.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      console.log(Math.round(1.33));
      console.log(Math.round(-28.7));
      console.log(Math.round(8.5));
      console.log(Math.round("101.45"));
   ```

   **Console Output**

   ```console
      1
      -29
      9
      101
   ```

{{% /notice %}}

`Math.round` also works on arrays, but must be combined with the
map array method. The syntax for this is:

```console
   arrayName.map(Math.round)
```

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      let numbers = [1.33, 4, 8.5, -15.523, 8.49];

      console.log(numbers.map(Math.round));
   ```

   **Console Output**

   ```console
      [ 1, 4, 9, -16, 8 ]
   ```

{{% /notice %}}