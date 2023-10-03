---
title: "style property Examples"
date: 2021-10-01T09:28:27-05:00
weight: 5
draft: false
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # update any time edits are made after review
reviewerGitHub: # update any time edits are made after review
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

The general syntax for the `style` property:

```javascript
element.style.aStyleProperty
```

The `style` property is an object that allows you to *read* and *update* the
INLINE style properties of the element. The `style` property does NOT *read*
or *update* styles defined in a `<style>` tag or an external CSS file linked with
a `<link>` tag.

{{% notice blue Example "rocket" %}}
```html
<!DOCTYPE html>
<html>
    <head>
    <title>DOM Examples</title>
    </head>
    <body>
    <h1>style property Example</h1>
    <div id="strawberry" style="color: red;">Strawberry</div>
    <div id="blackberry" style="color: purple; font-size: 5px">Blackberry</div>

    <script>
            let strawberry = document.querySelector("#strawberry");
            console.log(strawberry.style.color);
            let blackberry = document.querySelector("#blackberry");
            console.log(blackberry.style.fontSize);
            // Update the font size of strawberry
            strawberry.style.fontSize = "45px";
            console.log(strawberry.style.fontSize);
    </script>
    </body>
</html>
```

**Console Output**

```console
red
5px
45px
```
{{% /notice %}}