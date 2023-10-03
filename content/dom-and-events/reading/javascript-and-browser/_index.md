---
title: "JavaScript and the Browser"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Taking JavaScript on the Web

So far, we have created web pages with HTML and CSS. These pages have been **static**, meaning that the page appears the same each time it loads. 
However, you may find that you want to create a web page that changes after it's been loaded. In order to create such a page, you would use JavaScript.
Web pages that can change after loading in the browser are called **dynamic**.
This is useful to programmers and users alike because they can interact with an application without refreshing the page.
Having to constantly refresh the page would be a poor experience for the user and JavaScript helps programmers alleviate this burden.

{{% notice blue Example "rocket" %}}
When you are on a social media page, you may like someone's post.
When you do like their post, you may notice that several things happen.
The counter of how many likes the post has received increases by one and the 
like button may change color to indicate to you that you liked the post.
This is an example of how JavaScript could be used to create an application 
that dynamically updates without the page having to be refreshed.
{{% /notice %}}

We have been running all of our JavaScript code in Node.js, but now it is time to use JavaScript in the browser to make dynamic web pages. 
Node.js, or just Node, is a JavaScript interpreter with access to lots of different JavaScript libraries. 
Each browser has its own engine for running JavaScript. JavaScript run in the browser is called client-side JavaScript. 
Firefox uses an engine called Spider Monkey to run client-side JavaScript. 
Since each browser uses its engine, each browser may handle HTML, CSS, or JavaScript differently. 
This can lead to discrepancies between browsers.  

{{% notice orange Warning "rocket" %}}
The website [Can I Use](https://caniuse.com) is a great resource to check browser usability of any JavaScript, HTML or CSS.
{{% /notice %}}

### The `<script>` Tag

In the HTML chapter, we learned that an HTML page is made up of elements that are written as tags. Those
elements have different purposes. The `script` element's purpose is to include JavaScript into the
web page. A `<script>` tag can contain JavaScript code inside of it or reference an external JavaScript file.

### JavaScript Console

Using the Developer Tools, you can access a JavaScript console. There, you can mess around with fun JavaScript statements or you can use it to see the outputs of the client-side JavaScript you have written.

### Inline JavaScript

{{% notice blue Example "rocket" %}}
Notice the `<script>` tag below contains JavaScript code that will be executed by the browser.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Embedded JavaScript Example</title>
    <script>
        // JavaScript code goes here!
        console.log("Hello from inside the web page!");
    </script>
</head>
<body>
    contents
</body>
</html>
```

**Console Output**

```console
Hello from inside the web page!
```
{{% /notice %}}

### External JavaScript

Some programmers have large amounts of JavaScript to add to an HTML document.
Using an external JavaScript file can help in these cases.
You can still use the `<script>` tag to include the JavaScript file within the 
HTML document. In this case, you'll need to use the `src` attribute for the path 
to the JavaScript file.

{{% notice blue Example "rocket" %}}
This is how the HTML file for the web page might look if we wanted to link an external JavaScript file.

{{% /notice %}}

```html
<!DOCTYPE html>
<html>
<head>
    <title>External JavaScript Example</title>
    <script src = "myjs.js"></script>
</head>
<body>
    <!-- content -->
</body>
</html>
```

Then the JavaScript file, `myjs.js` might look something like this.

```javascript
// JavaScript code goes here!
console.log("Hello from inside the web page");
```

{{% notice blue Note "rocket" %}}
You can use the `<script>`  tag to reference JavaScript files hosted on external servers.
Some of these JavaScript files will be files that you have not written yourself but you will want to include in your application.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is the difference between dynamic and static web pages?
{{% /notice %}}

{{% notice green Question "rocket" %}}
Does Node.js run in the browser environment?
{{% /notice %}}