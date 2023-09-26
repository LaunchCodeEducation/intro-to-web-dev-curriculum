---
title: "Exercises: CSS"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

We have built a website for you to test your CSS knowledge. You can find the code within your `javascript-projects/css/exercises` directory!

{{% notice blue Note "rocket" %}}
Open the `index.html` file in your browser to view the application.

Utilize the `pwd` command to view your current working directory:

![Image of user entering the pwd to console](pictures/working-directory.png?classes=border)

The current working directory in the above image is `/home/john/Documents/launchcode/curriculum/exercises-studios/javascript-projects/css/exercises`

If you copy and paste the filepath after you run the `pwd` on your machine into a browser window and add `index.html` to the end of the string you will find your application.

![index-html file opened within browser window](pictures/index-html-browser.png?classes=border)
{{% /notice %}}

For the exercises, add the following style rules to the website:

1. Change the background color to yellow.

   {{% expand "Check Your Solution" %}}
   ```css
   body {
       background-color: yellow;
   }
   ```
   {{% /expand %}}

2. Change all paragraph text color to green.
3. Change all `h1` to 36 px font size.

   {{% expand "Check Your Solution" %}}
   ```css
   h1 {
       font-size: 36px;
   }
   ```
   {{% /expand %}}

4. Align all text to the center of the page.
5. Let's say that you don't like aligning all of the text to the center. Use a CSS class to align only the headings to the center of the page.

   {{% expand "Check Your Solution" %}}
   ```css
   .center {
       text-align: center;
   }
   ```
   {{% /expand %}}

6. Within `index.html` add a `center` class to all header tags (`h1`, `h2` etc.)

   {{% expand "Check Your Solution" %}}
   ```html
   <body>
      <h1 class="center">My Very Cool Web Page</h1>
      <h2 class="center">Why this Website is Very Cool</h2>
      <ol>
         <li>I made it!</li>
         <li>This website is colorful!</li>
      </ol>
      <h2 class="center" id="cool-text">Why I love Web Development</h2>
      <p>Web Development is a very cool skill that I love learning!</p>
      <p>I love making websites because all I have to do is reload the page to see the changes I have made!</p>
   </body>
   ```
   {{% /expand %}}

7. Change the font color of elements with the id, `cool-text`, to blue. 
8. Use a CSS id to change the elements in the ordered list to a color of your choosing.

   {{% expand "Check Your Solution" %}}
   ```css
   #list-color {
      color: blueviolet;
   }
   ```
   {{% /expand %}}

9. Within `index.html` add the `id` attribute to the `ol` tag.

   {{% expand "Check Your Solution" %}}
   ```html
   <ol id="list-color">
      <li>I made it!</li>
      <li>This website is colorful!</li>
   </ol>
   ```
   {{% /expand %}}

{{% notice blue Note "rocket" %}}
We learned from the reading that the location of CSS and the selector type can change the order of precedence of the CSS rules.
Try different locations and selector types and see what happens!
{{% /notice %}}