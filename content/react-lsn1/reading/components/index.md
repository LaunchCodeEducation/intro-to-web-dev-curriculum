---
title: "React Components"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

**Components** are the building blocks of React applications. Components are reusable, independent, and are responsible from individual elements of the webpage. For example, take a look at [Instacart](https://www.instacart.com/) and make note of elements of the webpage. You might see:

1. A button for logging into your account.
1. A button for signing up for a new account.
1. A section full of local to you stores so that you can select one you would like delivery from. 
1. Each store and vital information about them such as when items can be delivered by and a short byline about what the store sells.
1. Common questions have their own section that expands when the user clicks on it to reveal the answer.

Each of these elements might be a component in their React application. Components can be either **functional components** or **class components**. While there are no hard-and-fast rules on where components live in the application, best practice that we will be using in this class is placing each component in its own file and all of those files should live in a folder inside `src` called `components`. Components are then called in an `App` component where we would like them to appear on the page.

## Functional Components

Functional components are simply functions that return HTML. Later versions of React lean more on functional components than class components. Let's make a functional component that returns HTML about a local store.

```jsx
function SchnucksInfo() {
   return(
      <div>
         <h1>Schnucks</h1>
         <p>Grocery store</p>
         <p>Delivering within an hour</p>
      </div>
   );
}
```

If we have a functional component called `SchnucksInfo` in a separate file within the `components` directory, we have to export it and then import it in `App.jsx`.

```jsx
function App() {
  return (
    <div className="App">
      <SchnucksInfo />
    </div>
  );
}
```

Then we can run the application to see the rendered HTML of the `SchuncksInfo` component.

{{% notice blue "Note" "rocket" %}}
   Upon closer inspection, you may notice that `App` is also a functional component. 
{{% /notice %}}

Since your functional components are just functions, you can pass data to that component using **props**. Props is short for properties and are just the arguments passed to the components. We can write another functional component called `FavoriteFoodItem` and pass it an argument called `props`. Props are objects, so we need to access the data by the key you need. You can name your key whatever makes most sense given the context of your application, but that key is what you will use when calling your component to pass data with an HTML attribute. In the case of `FavoriteFoodItem`, we will need to use the value of `props.foodItem`. 

```jsx
function FavoriteFoodItem(props) {
   return(
      <div>
         <h2>Your favorite food item is {props.foodItem}!</h2>
      </div>
   );
}
```

Then when calling `FavoriteFoodItem` in `App`, let's pass `"butter"` to `FavoriteFoodItem`. To do so, we will add an HTML attribute called `foodItem` to our code. 

```jsx
function App() {
  return (
    <div className="App">
      <FavoriteFoodItem foodItem = "butter" />
    </div>
  );
}
```

If we ran the app, we would have a heading that said "Your favorite food item is butter!". 

## Class Components

Class components are classes that contain a `render()` method that returns the HTML we need and extend `React.Component`. This means when writing a class component, you have to `import React from 'react';`. Earlier versions of React rely on class components. While later versions make use of more functional components, you will still see class components in React codebases. Let's look at a class component for another local grocery store we want to get some groceries delivered from.

```jsx
class DierbergsInfo extends React.Component {
   render() {
      return(
         <div>
            <h1>Dierbergs</h1>
            <p>Grocery store</p>
            <p>Delivering within an hour</p>
         </div>
      );
   }
}
```

While `SchnucksInfo` and `DierbergsInfo` are structured differently, we can call `DierbergsInfo` the same way in `App.jsx` that we did `SchnucksInfo`.

```jsx
function App() {
  return (
    <div className="App">
      <DierbergsInfo />
    </div>
  );
}
```

## Check Your Understanding

{{% notice green "Question" "rocket" %}}
True/False: Functional components are functions that return HTML.
{{% /notice %}}

{{% notice green "Question" "rocket" %}}
True/False: Class components do not need a `render()` method.
{{% /notice %}}