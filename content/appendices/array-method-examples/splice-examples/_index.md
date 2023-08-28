---
title: "splice Examples"
date: 2021-10-01T09:28:27-05:00
weight: 10
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## `.splice()` Examples

The general syntax for this method is:

```javascript
arrayName.splice(index, number of elements to change, item1, item2, ...);
```

Inside the parentheses `()`, only the first argument is required.

The `splice` method modifies one or more elements anywhere in the array.
Entries can be added, removed, or changed. This method requires practice.

Hang on, here we go:

### Removing Elements

To remove elements from an array, the `splice` method needs 1 or 2 arguments.

1. Given only one argument, `splice(index)` removes every entry from `index` to the end of the array.

   {{% notice blue Example "rocket" %}}
   ```javascript
   let arr = ['a', 'b', 'c', 'd', 'e', 'f'];

   arr.splice(2);    //Everything from index 2 and beyond is removed.
   console.log(arr);
   ```

   **Output**

   ```console
   ['a', 'b']
   ```
   {{% /notice %}}         

1. With two arguments, `splice(index, number of items)` starts at `index`
   and removes the specified `number of items` from the array.

   {{% notice blue Example "rocket" %}}
   ```javascript
   let arr = ['a', 'b', 'c', 'd', 'e', 'f'];

   arr.splice(2,3);    //Start at index 2 and remove 3 total entries.
   console.log(arr);

   arr.splice(1,1);    //Start at index 1 and remove 1 entry.
   console.log(arr);
   ```



**Output**

```console
[ 'a', 'b', 'f' ]
[ 'a', 'f' ]
```
{{% /notice %}}


### Adding or Replacing Elements

To add or replace elements in an array, the `splice` method requires 3 or
more arguments.

1. To add elements, set the `number of elements` argument to `0` and follow this with the new items.

   {{% notice blue Example "rocket" %}}
   `splice(index, 0, new item)` starts at `index` and *INSERTS* the new items. Existing elements get shifted further down the array.

   ```javascript
   let arr = ['a', 'b', 'c', 'd', 'e', 'f'];

   arr.splice(2,0,'hello');     //Start at index 2, remove 0 entries, and add 'hello'.
   console.log(arr);
   ```

   **Output**

   ```console
   [ 'a', 'b', 'hello', 'c', 'd', 'e', 'f' ]
   ```
   {{% /notice %}}

1. To replace elements in an array, the `number of elements` argument must be a positive integer. Follow this with the new items for the array.

   {{% notice blue Example "rocket" %}}
   `splice(index, number of items, new items)` starts at `index` and *REPLACES* the `number of items` with the new ones.

   ```javascript
   let arr = ['a', 'b', 'c', 'd', 'e', 'f'];

   arr.splice(2,3,'hello', 9);    //Start at index 2, replace 3 entries with 'hello' and 9.
   console.log(arr);
   ```

   **Output**

   ```console
   [ 'a', 'b', 'hello', 9, 'f' ]
   ```
   {{% /notice %}}