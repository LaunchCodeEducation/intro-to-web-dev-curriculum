---
title: "More on Components"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 6
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

As we look at our components, we may want to style a component in a different manner than the rest of the app. We can do this in numerous ways, but we will teach you how to use CSS modules to do this. This is because CSS modules can be found in other codebases beyond React and do not require an external library to work. 

To create a CSS module to style our `Hello` component, all we need to do is create a new file in our `components` directory called `Hello.module.css`. We can then add a class with special styling, such as `helloText`. 

We then need to write an `import` statement to bring in our CSS classes and call them with HTML attributes.
To apply this, let's modify `Hello.js`:

```jsx
import styles from './Hello.module.css';

export default function Hello() {
   return(
      <div>
         <p className={styles.helloText}>Hello World!</p>
      </div>
   );
}
```

Now whatever the styling of `helloText` applies to our `<p>` tag in `Hello`!
