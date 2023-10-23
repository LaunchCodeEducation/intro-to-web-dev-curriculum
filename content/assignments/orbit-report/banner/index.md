---
title: "Task 2: Create the Banner Component"
date: 2023-05-25T11:39:25-05:00
draft: false
weight: 3
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Rob Thomas # to be set by the page reviewer
reviewerGitHub: icre8FreeCode # to be set by the page reviewer
lastEditor: Sally Steuterman # update any time edits are made after review
lastEditorGitHub: gildedgardenia # update any time edits are made after review
lastMod: 2023-10-16 # UPDATE ANY TIME CHANGES ARE MADE
---

### Create `Banner.jsx`

1. Create a new file named `Banner.jsx` inside the `components` directory.
1. Inside this file, create a function called `Banner`.  
   1. This function should return a `<header>` tag that says: "Orbit Report".
   1. Below the `<header>` create a `<p>` tag with instructions for users. 
   
      Here is an example message: 
      ```bash
      Click on the buttons to see the satellites in that orbit type
      ```
1. Make sure that you are exporting this function.
1. Open `App.jsx`
   1. Import the new `Banner` component you created.
   1. Nest the `Banner` component inside the `App()` function.

   ```react{linenos=table,hl_lines=[4],linenostart=10}
   function App() {
      return (
         <div>
            <Banner />
            <Buttons />
            <Table />
         </div>
      );
   }
   ```   

1. Check to see if your `Banner` renders.  

[Next]({{< relref "../../../assignments/orbit-report/update-app/" >}})
