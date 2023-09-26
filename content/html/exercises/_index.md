---
title: "Exercises: HTML"
date: 2023-09-19T14:37:14-05:00
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

In this course, we will mostly use Firefox as our browser. 
If you haven't installed Firefox, you can get it from [Mozilla](https://www.mozilla.org/en-US/firefox/new/). 
Other browsers have good developer tools as well (Chrome, in particular) but we're going to stick with Firefox. 
If you are more comfortable with another browser, you'll find that most of the developer tools functionality exists in other browsers' dev tools as well.

Complete the HTML file for this simple web page. Open up `javascript-projects/html/exercises`. Add lines to `index.html`
that do the following.

1. Add a `h1` to the page that says "Why I Love Web Development".
   
   {{% expand "Check Your Solution" %}}

   ```html
   <h1>Why I Love Web Development</h1>
   ```

   {{% /expand %}}

2. Add an ordered list to the page with 3 reasons why you love web development.
3. Add a link to this page below your list.

   {{% expand "Check Your Solution" %}}

   ```html
   <a href="https://www.webelements.com/" target="_blank">WebElements</a>
   ```
   
   {{% /expand %}}

4. Add a paragraph about the website you want to make with your web development
   superpowers!

This code block gives you a rough outline for how it might look.

```html {linenos=table}
<!DOCTYPE html>
<html>
   <head>
   </head>
   <body>
      <!-- h1 goes here --->
      <!-- ol goes here --->
      <!-- a goes here --->
      <!-- p goes here --->
   </body>
</html>
```

To see your work, open up `index.html` with Firefox. 
