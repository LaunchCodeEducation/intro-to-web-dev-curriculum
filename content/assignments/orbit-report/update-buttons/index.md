---
title: "Task 4: Update Buttons.js"
date: 2023-05-25T11:39:25-05:00
draft: false
weight: 5
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

### In this step, you will create the following:
1. Four clickable buttons
   1. Three of them will use the props you passed from the `App()` function
   1. One will display all of the satellites


### Inside the `Buttons.js` component:
1. Import the `satData` as `satData`.
1. Pass the props created from the `App()` function: `filterByType`, `setSat`, and `displaySats`.
1. Update the **first** button:
   1. This function needs to return a `<div>` that used the `map` function to iterate over the `displaySats` variable.
      1. Provide two callbacks for the `map` function: `id` and `sat`.
      1. The `map` function will return the first `<button>`.  
      1. Inside the `<button>` tag create the following:
         1. An `onClick` method that points to `filterByType()` function.  
         1. Set the `key` equal to `id`.
      1. Between the `<button>` tags, replace `"Placeholder Button"` with `{sat} Orbit`.

      ```react{linenos=table,hl_lines=[],linenostart=7}
      {displaySats.map((sat, id) => {
        return (
          <button onClick={() => filterByType(sat)} key={id}>
            {sat} Orbit
          </button>
        );
      })}
      //code continues
      ```
1. Update the **second** button:
   1. This button needs to be _outside_ of the `map` function.
   1. Inside the `<button>` tag, create an `onClick` function that points to `setSat`.  Pass `satData` to `setSat`. 

[Next]({{< relref "../../../assignments/orbit-report/update-table/" >}})
