---
title: "Math.abs Examples"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 1
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
   Math.abs(number)
```

This method returns the positive value of a number, which can be printed or
stored in a variable. `abs` works on both integer and decimal values.

Numerical strings can also be evaluated, but should be avoided as a best
practice.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=table}
      let num = Math.abs(-3);
      console.log(num);

      console.log(Math.abs(4.44));
      console.log(Math.abs('-3.33'));

      console.log(Math.abs(24/-3));
      // 24/-3 = -8
   ```

   **Console Output**

   ```console
      3
      4.44
      3.33
      8
   ```

{{% /notice %}}

`Math.abs` also works on arrays, but to make the process work, we must
combine it with the map array method. The syntax for this
is:

```console
   arrayName.map(Math.abs)
```

Note that `Math.abs` takes no argument when applied to an array.

{{% notice blue "Example" "rocket" %}}

   ```js {linenos=true}
      let numbers = [-2, 3, -4.44, "8.88"];

      let positiveArray = numbers.map(Math.abs);

      console.log(positiveArray);
   ```

   **Console Output**

   ```console
      [2, 3, 4.44, 8.88]
   ```

{{% /notice %}}