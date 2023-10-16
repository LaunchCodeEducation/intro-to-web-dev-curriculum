---
title: "Task 3: Update App.js"
date: 2023-05-25T11:39:25-05:00
draft: false
weight: 4
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: Sally Steuterman # update any time edits are made after review
lastEditorGitHub: gildedgardenia # update any time edits are made after review
lastMod: 2023-10-16 # UPDATE ANY TIME CHANGES ARE MADE
---

### In this step, you will create the following:
1. A variable to manage the state of our project
1. A variable to hold the unique values of the `orbitType` property of the satellite objects
1. A function that will filter through the satellites.

These variables and this function will be used by the `Buttons` and `Table` components.

### Inside the `App.jsx` file
Open the `App.js` file.  

1. Import `useState` from `"react"`.
1. Import `satData.jsx` as `satData`.
1. Inside the `App()` function create the first variable.
   ```react{linenos=table,hl_lines=[],linenostart=7}
   function App() {
      const [sat, setSat] = useState(satData);
      // code continues ...
   ```
   This array holds two variables: `sat` and `setSat`.  `sat` will be used to compare changes in state.  `setSat` is a function that will be used to update the state.  We set this array equal to the `useState` function.  `useState` is passed `satData`. You will use these in the other components.

1. Next, create the second variable, called `displaySats`.  
      ```react{linenos=table,hl_lines=[3],linenostart=7}
      function App() {
         const [sat, setSat] = useState(satData);
         const displaySats = [...new Set(satData.map((data) => data.orbitType))];
         // code continues ...
      ```
   This variable will use the `Set` [method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) to create a new array that holds unique elements.  This function will be used to create the buttons, so we want to pull out the `orbitType` values of each object inside `satData`.  The `Set` method prevents duplicate elements.  We are using it because there are only three types of `orbitTypes`: Low, Medium, and High.  This will eventually create three buttons.  If we only used map, we would create 10 buttons, and many of them would be duplicates. 

1. Next, create an arrow function called `filterByType`.  
   1. This function will take a parameter that you can call `currentType`.
   1. Inside this function, you will update the `displaySats` variable using the `filter` [method](https://upmostly.com/tutorials/react-filter-filtering-arrays-in-react-with-examples).  
      1. `filter` is similar to `map`, in that it will iterate through a collection until it finds the desired element.
   1. `filter` requires a callback, call the callback `newSatDisplay`.  
   1. The `filter` function will return the `newSatDisplay.orbitType` that is equal to `currentType`.  
   1. Close the `filter` function's return statement.  
   1. Before closing the arrow function, we want to update `setSat` by passing it the newly updated `displaySats`.  

   ```react{linenos=table,hl_lines=[],linenostart=11}
   const filterByType = (currentType) => {
      const displaySats = satData.filter((newSatDisplay) => {
         return newSatDisplay.orbitType === currentType;
      });
      setSat(displaySats);
   };
   ```
1. Before we leave the `App()` function, we need to provide props for the `Buttons` and `Table` components.
   ```react{linenos=table,hl_lines=[],linenostart=11}
    <>
      <Banner />
      <Buttons
        filterByType={filterByType}
        setSat={setSat}
        displaySats={displaySats}
      />
      <Table sat={sat} />
    </>
   ```

[Next]({{< relref "../../../assignments/orbit-report/update-buttons/" >}})



