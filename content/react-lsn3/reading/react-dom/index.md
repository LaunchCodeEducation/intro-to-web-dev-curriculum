---
title: "React and the DOM"
date: 2023-04-12T16:25:46-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

When changing the state, our intended effect may involve using some of the methods and processes we learned about earlier when we first talked about the [DOM and events](https://education.launchcode.org/intro-to-professional-web-dev/chapters/dom-and-events/index.html). Let's take a closer look at changing state with an application in manufacturing.

We are at a shoe factory and the mechanism responsible for counting how many shoes come off the line is broken. The factory manager doesn't want to stop production and cause unnecessary delays so they have asked you to sit by the machine and manually count the shoes coming down the line. With your React skills, you can quickly code an application that contains a single button and displays the current shoe count.

1. Create a new React application using Create-React-App. 
1. Make a new `components` directory.
1. Make a new file called `ShoeButton.js`.
1. Add the following code to that file.

   ```jsx {linenos=table}
      import { useState } from 'react';

      export default function ShoeButton() {
         const [shoeCount, setShoeCount] = useState(0);

         const handleClick = () => {
            setShoeCount(shoeCount+1);
         }

         return (
            <div>
               <h1>{shoeCount} shoes have come down the line!</h1>
               <button onClick={handleClick}>Add a shoe!</button>
            </div>
         );
      }
   ```

1. Add a call to your `ShoeButton` component to `App.js`.
1. Run the application and start hitting the button to update the state!

This is an example of a counter button, which is one of the simplest ways to update the state of a component. You may have noticed that as you click the button, the page doesn't reload, but the component still re-renders. Here is what is happening:

1. When you click the button, the call to `setShoeCount` inside `handleClick()` updates the value of the state variable, `shoeCount`.
1. This call ensures that the change in state is recognized and that component re-rendering is triggered. 
1. React's Virtual DOM then updates the `<h1>` element to display the new shoe count.
1. React compares the real DOM to the Virtual DOM and finds that the real DOM has the old shoe count displayed and the virtual DOM has the new shoe count displayed.
1. Reconciliation occurs and the real DOM is updated to display the new count.
1. Now the component is re-rendered and you can hit the button again!

In this code, `handleClick()` is our event handler for the `onClick` event. We previously learned about `onClick` in [DOM and Events](https://education.launchcode.org/intro-to-professional-web-dev/chapters/dom-and-events/events.html?highlight=onclick#handling-events). In React, we use event handlers to trigger changes in state based on users' actions. You may have noticed that we are able to write web applications that perform similar actions as the ones we learned about previously with much less code.

When we first learned about event handlers, we created a small application that would update some HTML when a button was clicked.

```html {linenos=table}
   <!DOCTYPE html>
   <html>
      <head>
         <title>Button click handler</title>
         <script>
            function youRang() {
               document.getElementById("main-text").innerHTML += "you rang...";
               console.log("you rang...");
            }
         </script>
      </head>
      <body>
         <h1>Ring the Doorbell!</h1>
         <p id="main-text"></p>
         <button onclick="youRang();">Ring Bell</button>
      </body>
   </html>
```

With React, we can simplify our code and still accomplish the same task.

```jsx {linenos=table}
   import { useState } from 'react';

   export default function Doorbell() {
      const[bell, setBell] = useState("");

      const handleClick = () => {
         setBell(bell += "you rang...");
      }

      return(
         <div>
            <h1>Ring the Doorbell!</h1>
            <p>{bell}</p>
            <button onclick="handleClick">Ring Bell</button>
         </div>
      );
   }
```

{{% notice blue "Note" "rocket" %}}

   Typically, event handlers in React applications are named using the following convention: "handle" + name of event.
   Hence, the event handler for handling the event of clicking on the button is "handleClick". You will also see names like "handleSubmit" or "handleChange".

{{% /notice %}}