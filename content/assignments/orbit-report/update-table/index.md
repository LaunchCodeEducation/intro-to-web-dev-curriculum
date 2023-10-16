---
title: "Task 5: Update Table.js"
date: 2023-05-25T11:39:25-05:00
draft: false
weight: 6
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: Sally Steuterman # update any time edits are made after review
lastEditorGitHub: gildedgardenia # update any time edits are made after review
lastMod: 2023-10-16 # UPDATE ANY TIME CHANGES ARE MADE
---

### In this step, you will create the following:
A table that provides the following data about the satellites: 
   1. Name
   1. Type of Satellite
   1. Launch Date
   1. Status

Comments have been provided to help structure the table.  You can keep them or remove them.

### Inside the `Table.jsx` component:

1. Notice that the `Table` function starts with the `sat` prop provided.
1. Start by updating the table header.  It needs a total of four `<th>` tags.  They need to hold text for the following data points: Name, Type of Satellite, Launch Date, and Status.
1. The body of the table will use the `map` function to render the data based on which button a user selects.
1. Iterate through the `sat` prop using `map`; use the following callbacks: `id` and `data`.
   1. The `map` function will return data to each row in the table.  
   1. The `<tr>` tag in the table body needs a `key`.  Set the `key` equal to the `id`.
   1. Create a total of four `<td>` tags.
      1. Use dot notation to assign the correct object key.  The code below would render the name of a satellite.
      ```html
      <td>{data.name}</td>
      ```
      1. The value for each `<td>` tag needs to correspond to the `<th>` tags.  This means that we want names of satellites to be rendered in a column of names.
1. For the `Status`, create a conditional that will tell a user if a satellite is active or inactive based on its `operational` value.

### Status Check

You should have a Banner, four buttons, and a table.  When you click on a button, satellites with the selected orbit type should be rendered.

**Great job!**  You are ready for the next steps.


[Step 6]({{< relref "../../../assignments/orbit-report/styling/" >}}) contains optional styling features.  You can skip this step, if you would like. 


[Step 7]({{< relref "../../../assignments/orbit-report/testing/" >}}) contains information for running the auto-grading tests.  You will need to do step 7. 