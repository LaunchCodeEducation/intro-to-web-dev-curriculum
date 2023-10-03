---
title: "Event Types"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 6
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewesr
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

DOM and JavaScript can handle numerous event types. We will discuss a few different types of events here.
As you continue your studies of the DOM and events, you may find these two reference links helpful.

1. [W3Schools Event reference](https://www.w3schools.com/jsref/dom_obj_event.asp).
2. [MDN Event reference](https://developer.mozilla.org/en-US/docs/Web/Events).

## `load` Event

The DOM includes the **load event**, which is triggered when the window, elements, and resources have
been *loaded* by the browser. Why is it important to know when things have loaded? Remember you can't
interact with HTML elements in JavaScript unless they have been loaded into the DOM.

Previously, we were moving the `<script>` element *below* any HTML elements that we needed
to reference in the DOM. Using the `load` event on the global variable `window` is an
alternative to `<script>` placement. When the `load` event has triggered on the `window` as
a whole, we can know that all the elements are ready to be used.

{{% notice blue Example "rocket" %}}
A `<script>` tag is in `<header>` and all DOM code is inside `load` event handler.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Window Load Event</title>
    <script>
    // add load event handler to window
    window.addEventListener("load", function() {
        // put DOM code here to ensure elements have been loaded
        console.log('window loaded');

        let ring = document.getElementById("ring-button");
        ring.addEventListener("click", function (event) {
            console.log("ring ring");
        });

        let knock = document.getElementById("knock-button");
        knock.addEventListener("click", function (event) {
            console.log("knock knock");
        });
    });
    </script>
</head>
<body>
    <div id="toolbar">
    <button id="ring-button">Ring Bell</button>
    <button id="knock-button">Knock on Door</button>
    </div>
</body>
</html>
```

**Console Output** (if "Knock on Door" button is clicked)

```console
window loaded
knock knock
```
{{% /notice %}}

## `mouseover` and `mouseout` Events

There are many mouse related DOM events. We have already used the `click` event. Another example
of a mouse event is the **mouseover event**, which is triggered when the mouse cursor enters
an element.

{{% notice blue Example "rocket" %}}
We can use `mouseover` event to add a `">"` to the `innerHTML` of the element that the mouse cursor has been moved over.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Mouseover Event</title>
    <script>
        window.addEventListener("load", function() {
            let list = document.getElementById("lane-list");
            list.addEventListener("mouseover", function (event) {
                let element = event.target;
                element.innerHTML += ">";
                console.log("target", element);
            });
        });
    </script>
</head>
<body>
    Mouseover Race
    <ul id="lane-list">
        <li>Lane 1</li>
        <li>Lane 2</li>
        <li>Lane 3</li>
    </ul>
</body>
</html>
```

**Example HTML Output** (if the mouse is moved over elements in the list)

```console
Mouseover Race

    Lane 1>>>>>>>
    Lane 2>>>>>>>>>>>>
    Lane 3>>>>>>>>
```
{{% /notice %}}

Similarly, there is a **mouseout event** that is triggered when the cursor leaves a given element.

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which error occurs when you try to access an element that has not been loaded into the DOM?
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is *true* when the `load` event is triggered on `window`?

1. The console is clear.
1. All elements and resources have been loaded by the browser.
1. Your files have finished uploading.
{{% /notice %}}