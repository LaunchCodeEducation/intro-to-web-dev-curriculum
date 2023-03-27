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

In the JavaScript landscape, we can use a JavaScript syntax extension. One such extension is **JSX** or **JavaScript XML**.
React developers use JSX to write HTML elements inside our JavaScript code.

With JSX, we can assign some HTML to a variable like so:

```jsx
   let newElement = <h1>This is a new element!</h1>;
```

Behind the scenes, our React app will use this line of code to create a new HTML element that can be passed on to the browser.

## JavaScript in JSX

Now that we can use HTML in our JavaScript code with JSX, you might be wondering how to pass JavaScript values to HTML expressions, such as the value of a variable. To do this, we wrap the JavaScript code in `{}`. Let's see how we could use this to pass the value of a hiker's name in our theoretical hiking application.

```jsx
   let hikersName = "Rob";
   let welcomePage = <h1>Welcome, {hikersName}!</h1>;
```

If we were to run this code, the value of `hikersName`, "Rob", would be passed to `welcomePage` so when the page rendered, you would have an `h1` element that said "Welcome, Rob!". Wrapping the variable in curly braces gives our hiking application the flexibility to display a custom welcome page for the hiker once they log into their account. If `hikersName` had a different value than the `h1` element would render with that value instead.

### Comments 

Now you might be wondering what comments look like in JSX. You can start a comment with `{/*` and then end a comment with `*/}`. 

```jsx
   {/* Pass value of hiker's name to welcomePage element */}
   let hikersName = "Rob";
   let welcomePage = <h1>Welcome, {hikersName}!</h1>;
```

### Limitations

Because you have to wrap your JavaScript expressions when writing JSX, there are some things you cannot write the way you used to when you are writing something inside `{}`:

1. Loops
1. Variable declaration
1. Function declaraction
1. `if/else` conditions
1. objects

We can, however, use ternary operators to write conditional expressions inside curly braces.

```jsx
   a > b ? a - b : a + b 
```

The above code states that *if* `a` is greater than `b` than subtract the value of `b` from the value of `a`. Otherwise, add the value of `b` to the value of `a`. Whatever comes before the question mark is the condition that is checked. The expression between the question mark and the colon is what should execute if the condition evaluates to true and if it is false, then the expression after the colon will execute.

