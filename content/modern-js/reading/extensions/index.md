---
title: "JavaScript Syntax Extensions"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In the JavaScript landscape, we can use a JavaScript syntax extension. A **syntax extension** adds new syntax rules that are not a regular feature of the base programming language. Adding new syntax features to programming languages is a large lift and can lead to frustration and confusion amongst the developer community. However, if there is a specific use case that would benefit from new syntax rules, language developers may create a syntax extension to allow a small set of developers to access that beneficial syntax without impacting the base language. One such extension for JavaScript is **JSX** or **JavaScript XML**. JSX syntax allows developers to write HTML elements inside JavaScript code without having to handle any of the rendering themselves. React developers use JSX because it efficiently renders components of web applications.

For example, with JSX, we can assign some HTML to a variable like so:

```jsx
   let newElement = <h1>This is a new element!</h1>;
```

Behind the scenes, our React app will use this line of code to create a new HTML element that can be passed on to the browser. You will notice that we didn't have to handle any of this rendering. All we had to do was write a small heading!

## Rendering data in JSX

One task that we will need to take on as JavaScript developers is rendering data values in our application. If we turn our attention back to our hiking application, we may want to create a customized welcome page for the users after they log in to their accounts. We can store the value of a user's name in a variable called `hikersName`. Let's try and write some JSX.

```jsx
   let hikersName = "Mo";
   let greeting = <h1>Welcome, hikersName!</h1>
```

If we ran this code in our browser, it would just say "Welcome, hikersName!". We want to render the value of the `hikersName` variable not the name of the variable. To do so, we need to wrap JavaScript expressions in HTML in curly braces to ensure that when the page is rendered, we are clear on what is HTML and what is JavaScript.

```jsx
   let hikersName = "Mo";
   let greeting = <h1>Welcome, {hikersName}!</h1>
```

Now if we were to run this code, the value of `hikersName`, "Mo", would be passed to `greeting` so when the page rendered, you would have an `h1` element that said "Welcome, Mo!". Wrapping the variable in curly braces gives our hiking application the flexibility to display a custom welcome page for the hiker once they log into their account. If `hikersName` had a different value than the `h1` element would render with that value instead.

### Comments 

Now you might be wondering what comments look like in JSX. You can start a comment with `{/*` and then end a comment with `*/}`. 

```jsx
   {/* Pass value of hiker's name to welcomePage element */}
   let hikersName = "Mo";
   let greeting = <h1>Welcome, {hikersName}!</h1>
```

### Limitations

Because you have to wrap your JavaScript expressions when writing JSX, there are some things you cannot write the way you used to when you are writing something inside `{}`:

1. Loops
1. Variable declaration
1. Function declaration
1. `if/else` conditions
1. objects

However, there are some workarounds that you will learn more about as we dive into React further.

## Check Your Understanding

{{% notice green "Question" "rocket" %}}
   True/False: I can write a loop wrapped in a JavaScript expression in JSX.
{{% /notice %}}

{{% notice green "Question" "rocket" %}}
   True/False: I cannot write HTML with JSX. JSX is just JavaScript but with a cooler name.
{{% /notice %}}