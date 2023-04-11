---
title: "Make a New Component"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

With your application set up, you are ready to make your first component.

## Creating a Component

1. Create a directory called `components` within `src`.
1. Inside `components` make a new file called `Hello.js`
1. Write a function called `Hello` that does not have any parameters and returns a `<div>` that contains one `<p>` tag that just says "Hello World!".
1. At the front of your function declaration add `export default`. This will allow us to import it into other files.

At this point, your `Hello.js` file should look something like this:

```jsx
export default function Hello() {
   return(
      <div>
         <p>Hello World!</p>
      </div>
   );
}
```

{{% notice orange "Warning" "rocket" %}}
   Components can only return one parent element of HTML. If you look at the code above, the `<div>` is the parent element and `<p>` is the child element. If we placed the `<p>` tag *outside* of the `<div>` tag, we would get an error and the app would not run. As you add more and more HTML to a component, make sure that your code only has one parent element!
{{% /notice %}}

## Calling Your Component

If you ran your app, you wouldn't see your new component. Time to change that by calling it in the `App` component.

1. Inside `src`, locate `App.js`.
1. Add an `import` statement to the top of `App.js` importing your component from the correct file. In this case, your `import` statement would look like: `import Hello from './components/Hello.js'`.
1. Inside the `App()` function, *within* the `<div>` tag that has `className="App"` as its attribute, replace the current code with `<Hello />`. 

At this point, your `App` component should look something like this:

```jsx
function App() {
  return (
    <div className="App">
      <Hello />
    </div>
  );
}
```

Run your application using `npm start` to see your rendered component!