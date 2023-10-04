---
title: "confirm Examples"
date: 2021-10-01T09:28:27-05:00
weight: 1
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
let answer = window.confirm("Message to user");
```

Displays a dialog box with a message and returns `true` if user clicks "ok" and `false` if user clicks "cancel".
The browser waits until the user clicks "ok" or "cancel".

{{% notice blue Example "rocket" %}}
```javascript
let response = window.confirm("Would you like to play a game?");
// Code does NOT continue until user responds to confirm window
if (response) {
    console.log("Let's play a board game");
} else {
    console.log("Oh well, let's code instead");
}
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
Remember that methods defined on `window` can be used without referencing the `window` variable.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```html
<!DOCTYPE html>
<html>
    <head>
    <title>DOM Examples</title>
    </head>
    <body>
    <h1>Window Confirm Example</h1>
    <script>
            let response = confirm("Are you excited?");
            if (response) {
                console.log("Yay! Me too!");
            } else {
                console.log("Oh no! I hope tomorrow is a better day!");
            }
    </script>
    </body>
</html>
```

**Console Output** (If "cancel" clicked)

```console
Oh no! I hope tomorrow is a better day!
```
{{% /notice %}}