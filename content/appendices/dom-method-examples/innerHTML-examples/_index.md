---
title: "innerHTML Examples"
date: 2021-10-01T09:28:27-05:00
weight: 4
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

The general syntax for the `innerHTML` property is:

```javascript
element.innerHTML
```

The innerHTML property of elements *reads* and *updates* the HTML and or text that is
inside the element.

{{% notice blue Note "rocket" %}}
The `innerHTML` value for empty elements is empty string `""`.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```html
<!DOCTYPE html>
<html>
    <head>
    <title>DOM Examples</title>
    </head>
    <body>
    <h1>innnerHTML Example</h1>

    <h2>Yellow Fruits</h2>
    <ul class="yellow">
        <li>Banana</li>
    </ul>

    <script>
        let ul = document.querySelector(".yellow");
        console.log(ul.innerHTML.trim());
    </script>
    </body>
</html>
```

**Console Output**

```console
<li>Banana</li>
```
{{% /notice %}}

{{% notice green Tip "rocket" %}}
Use `.trim` to remove the whitespace around the value of `.innerHTML`
{{% /notice %}}

As mentioned above `innerHTML` can be used to read and *update* the contents of an element.
`innerHTML` is so powerful that you can pass in strings of HTML.

{{% notice blue Example "rocket" %}}
```html
<!DOCTYPE html>
<html>
    <head>
    <title>DOM Examples</title>
    </head>
    <body>
    <h1>innnerHTML Example</h1>

    <h2>Yellow Fruits</h2>
    <ul class="yellow">
        <li>Banana</li>
    </ul>

    <script>
        let ul = document.querySelector(".yellow");
        // Add a <li> to the list
        ul.innerHTML += "<li>Lemon</li>";
        console.log(ul.innerHTML.trim());
    </script>
    </body>
</html>
```

**Console Output**

```console
<li>Banana</li>
<li>Lemon</li>
```
{{% /notice %}}