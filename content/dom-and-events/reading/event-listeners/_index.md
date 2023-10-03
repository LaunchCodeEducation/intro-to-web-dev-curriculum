---
title: "Event Listeners"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 5
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Using inline event handling is a good way to get started handling events. A second way
to handle events uses the DOM objects and methods. Remember, the DOM is an object representation
of the entire web page. The DOM allows us to use JavaScript to configure
our event handlers. The event handling declaration will no longer be in the HTML
element attribute, but will instead be inside `<script>` tags or in an external JavaScript file.


## Add Event Handlers in JavaScript

Before we add event handlers in JavaScript, we need to learn a new vocabulary term related to
events in programming. A **listener** is another name for an event handler. The term
listener refers to the code *listening* for the event to occur. If the code *hears* the event,
then the event is handled.

`addEventListener` is used to add an event handler, aka *listener*. `addEventListener`
is a method available on instances of `Window`, `Document`, and `Element` classes.

```javascript
anElement.addEventListener("eventName", aFunction);
```

`anElement` is a reference to a DOM element object. `"eventName"` is the name of an event that
the variable `anElement` supports. `aFunction` is a reference to a function. To start, we are
going to use a *named function*.

{{% notice blue Example "rocket" %}}
We want to set the named function `youRang` as the *click* handler for the 
`button` element. Notice that the value passed in as the event name is 
`"click"` instead of `"onclick"`.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Use addEventListener</title>
</head>
<body>
    <p id="main-text" class="orange" style="font-weight: bold;">
    a bunch of really valuable text...
    </p>
    <button id="ring-button">Ring Bell</button>
    <script>
    function youRang() {
        document.getElementById("main-text").innerHTML += "you rang...";
        console.log("you rang...");
    }
    // Obtain a reference to the button element
    let button = document.getElementById("ring-button");
    // Set named function youRang as the click event handler
    button.addEventListener("click", youRang);
    </script>
</body>
</html>
```

**Result** (if button is clicked)

```console
affect on page: adds "you rang..." to <p>
output in console: you rang...
```
{{% /notice %}}

{{% notice orange Warning "rocket" %}}
Be sure to use the correct event name when declaring the event name. An error will NOT be thrown
if an invalid event name is given.
{{% /notice %}}

{{% notice blue Note "rocket" %}}
This chapter uses DOM methods to add event handlers. When searching online, you may find examples
using jQuery to add event handlers, which look like `.on("click", ...)` or `.click(...)`.
**jQuery** is a JavaScript library designed to simplify working with the DOM. jQuery's popularity
has declined as the DOM itself has gained features and improved usablity.
{{% /notice %}}

The second parameter of `addEventListener` is a function. Remember there are many ways to declare a
function in JavaScript. So far, we have passed in named functions as the event handler.
`addEventListener` will accept any valid function as the event handler. It's possible, 
and quite common, to pass in an *anonymous function* as the event handler.

```javascript
anElement.addEventListener("eventName", function() {
    // function body of anonymous function
    // this function will be executed when the event is triggered
});
```

## Event Details

A benefit of using `addEventListener` is that an *event* parameter can be passed to 
the event handler function. This event is an object instance of the Event 
class, which defines methods and properties related to events.

```javascript
anElement.addEventListener("eventName", function(event) {
    console.log("event type", event.type);
    console.log("event target", event.target);
});
```

`event.type` is a string name of the event.

`event.target` is an element object that was the target of the event.

{{% notice blue "Try It!" "rocket" %}}
Above, we saw how we could use `addEventListener` to add the function `youRang()` as the event handler for the `Ring Bell` button.

Using `addEventListener`, could you add the function `greetFriends()` as the event handler for the `Greet Friends` button?
{{% /notice %}}

## Event Bubbling

Remember that the DOM is a tree of elements with an `<html>` element at the root. The tree
structure of an html page is made of elements inside of elements. That layering effect can cause
some events, like *click*, to be triggered on a series of elements. **Bubbling**
refers to an event being propagated to ancestor elements, when an event is triggered on an
element that has parent elements. Events are triggered first on the element that is most closely
affected by the event.

{{% notice blue Example "rocket" %}}
We can add a *click* handler to a `<button>`, a `<div>`, and the `<html>` element via the `document`
global variable.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Event Bubbling</title>
    <style>
    #toolbar {
        padding: 20px;
        border: 1px solid black;
        background-color:darkcyan;
    }
</style>
</head>
<body>
    <div id="toolbar">
    <button id="ring-button">Ring Bell</button>
    </div>
    <script>
    let button = document.getElementById("ring-button");
    button.addEventListener("click", function (event) {
        console.log("button clicked");
    });
    document.getElementById("toolbar").addEventListener("click", function (event) {
        console.log("toolbar clicked");
    });
    document.addEventListener("click", function (event) {
        console.log("document clicked");
    });
    </script>
</body>
</html>
```

**Console Output** (if button is clicked)

```console
button clicked
toolbar clicked
document clicked
```
{{% /notice %}}

In some cases, you may want to stop events from bubbling up. We can use `event.stopPropagation()` to stop
events from being sent to ancestor elements. Handlers for parent elements will not be triggered if
a child element calls `event.stopPropagation()`.

```javascript
button.addEventListener("click", function (event) {
    console.log("button clicked");
    event.stopPropagation();
});
```

{{% notice green "Try It!" "rocket" %}}
With the HTML above, what happens when you click in the green?

After you see the result, try adding `stopPropagation()` to the button click handler and seeing what happens when you click the button.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Do these code snippets have the same effect? `button.addEventListener("click", youRang)` and `<button onclick="youRang();">`
{{% /notice %}}

{{% notice green Question "rocket" %}}
Can *click* events be prevented from bubbling up to ancestor element(s)?
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is passed as the *argument* to the event handler function?
{{% /notice %}}