---
title: "An Introduction to State in React"
date: 2023-04-12T16:25:46-05:00
draft: false
weight: 1
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

One of the benefits of using React is that as users interact with the application, the application updates the user interface without reloading the entire page. This is due to a concept called **state**. State is oftentimes referred to as a component's memory. 

Let's think back to the last time you filled out your tax return. If you e-file your taxes, you might have used a React-based web application to do so. An example component would be the tax estimate for your federal and state taxes. For some tax applications, if it looks like you are getting a refund, the number is green and if it looks like you owe some money, the number is red. At the beginning of the process, both federal and state would have shown $0 or "N/A" to indicate that you haven't started the process yet. Now when you enter the information on a form, like your W2, you see the numbers in that component changing. In fact, every time you edit some aspect of your taxes, the numbers may change and the colors of that number may change. This is where state comes into play in this React-based tax application. Reloading the page every time you edit one thing would be annoying and make the application inefficient. Even just re-rendering one component on the page can be a costly process. With state, the component is only re-rendered when there is new data. If you enter some information that doesn't change the fact that the federal government owes you a refund of $200, the component will not re-render. Selectively re-rendering components makes React an efficient library to use for web development. While not always noticeable, re-rendering components can lead to lagging or delays as the users interacts with your application. By only re-rendering components in select cases, React helps us minimize the possibility of this happening.

While state is a built-in concept in React, you as the programmer have to call upon it. Local variables won't keep their values during re-renders and changing the value of a local variable doesn't trigger re-rendering. We have to use a **state variable** to hold data that we want to keep as part of the component's memory. To set the value of a state variable, we will use a **state setter function**. Both a state variable and state setter function are provided by a React hook called `useState()`. **Hooks** are features of React that allow you to access different aspects of React and use them with your components. Without hooks, components would just be ordinary classes and functions.

In the example of a tax application, we might have a state variable for federal taxes called `federalTax`. We can then declare that state variable like so:

```jsx
   const [federalTax, setFederalTax] = useState(0);
```

Here we are using the `useState` hook to set the initial value of `federalTax` to 0. We also have declared that the state setter function for `federalTax` is `setFederalTax`. To update the value of `federalTax` to 100, we just have to use `setFederalTax` like so, `setFederalTax(100)`. 

You can also set up the state variable to be an object. Here is how we might do it with our tax application.

```jsx
   const [taxes, setTaxes] = useState({
      federal: 0,
      state: 0
   });
```

With `useState`, the value of `taxes.federal` is set to 0 and the value of `taxes.state` is also set to 0. To update the value of the state taxes to -10, but not update the value of the federal taxes, then we would pass those values to `setTaxes` like so:

```jsx
   setTaxes({
      federal: taxes.federal,
      state: -10
   });
```

State variables are considered read-only, so in order for us to update the state, we have to pass a new object to the state variable.

{{% notice orange "Warning" "rocket" %}}
   It is worth noting that if the user reloads the page, the state of the component is returned to the original state. If we wanted to make sure that we didn't lose track of what the user owes in federal taxes, we may have to do some backend work, but that is a task for Unit 2 of this course.
{{% /notice %}}

## Check Your Understanding

{{% notice green "Question" "rocket" %}}
   What is `useState`?

   1. A class
   1. An object
   1. A hook
   1. A function

{{% /notice %}}

<!-- A hook -->

{{% notice green "Question" "rocket" %}}
   True or False: State variables are considered to be read-only.
{{% /notice %}}

<!-- True -->