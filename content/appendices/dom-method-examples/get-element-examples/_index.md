---
title: "getElementById Examples"
date: 2021-10-01T09:28:27-05:00
weight: 2
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

The general syntax for this method is:

```javascript
let element = document.getElementById("element-id");
```

Searches the HTML document for an element that has an *id* attribute that matches the string
parameter. Returns a reference to the matching element object if match found. If NO matching
element is found, `null` is returned.

{{% notice blue Example "rocket" %}}
```html
<!DOCTYPE html>
<html>
    <head>
    <title>DOM Examples</title>
    </head>
    <body>
    <h1>getElementById Example</h1>
    <p id="description">
        This will be turned blue.
    </p>
    <script>
        let paragraph = document.getElementById("description");
        console.log("paragraph contents:", paragraph.innerHTML.trim());
        paragraph.style.color = "blue";
    </script>
    </body>
</html>
```

**Console Output**

```console
paragraph contents: This will be turned blue.
```
{{% /notice %}}

{{% notice green Tip "rocket" %}}
Because `getElementById` returns `null` if an element with a matching id can NOT be found, you
could see a message like `TypeError: paragraph is null`. Be sure to double check the id you are using
in JavaScript and in the HTML.
{{% /notice %}}