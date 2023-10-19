---
title: "Make a New Component"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 5
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

With your application set up, you are ready to make your first component.

## Creating a Component

1. Create a directory called `components` within `src`.
1. Inside `components` make a new file called `Hello.jsx`
1. Write a function called `Hello` that does not have any parameters and returns a `<div>` that contains one `<p>` tag that just says "Hello World!".
1. At the front of your function declaration add `export default`. This will allow us to import it into other files.

At this point, your `Hello.jsx` file should look something like this:

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

### Refactoring default App.jsx

1. Inside `src`, locate `App.jsx`.

The default `App.jsx` file will look like the following code block:

```jsx {linenos=true hl_lines=[2, 3, 7, 12, 13, 14, 15, 16, 17, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30]}
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'

function App() {
  const [count, setCount] = useState(0)

  return (
    <>
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
    </>
  )
}

export default App
```

Remove all highlighted lines as shown above and add the following code below:

2. Add an `import` statement to the top of `App.jsx` importing your component from the correct file. In this case, your `import` statement would look like: `import Hello from "./components/Hello"`.
3. Inside the `App()` function, *within* the `<div>` tags, add the following line: 

   ```jsx
   <Hello />
   ```
At this point, your `App.jsx` component should look something like this:

```jsx
import { useState } from 'react'
import './App.css'
import Hello from "./components/Hello";

function App() {

  return (
   <>
      <div>
	      <Hello />
      </div>
   </>
  )
}

export default App
```

Run your application using `npm run dev` to see your rendered component!