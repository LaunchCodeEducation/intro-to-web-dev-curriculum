---
title: "Events"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 4
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Have you ever thought about how programs respond to interactions from users and other
programs? **Events** are code representations of these interactions that need to be responded to.

> In programming, events are triggered and then handled.

*Events in programming are triggered and handled*. **Triggering** an event is
the act of causing an event to be sent. **Handling** an event is receiving the
event and performing an action in response.


## JavaScript and Events

JavaScript is an event-driven programming language. **Event-driven** is a programming
pattern where the flow of the program is determined by a series of events. JavaScript
uses events to handle user interaction and make web pages dynamic. JavaScript also uses
events to know when the state of the web page components change.


## DOM Events

Running JavaScript in the browser requires a specific set of events that relate to loading,
styling, and displaying HTML elements. Objects in the DOM have event handling built right
into them.

Some elements, such as `a`, have default functionality that handles certain events. An
example of default event handling is when a user clicks on an `<a>` tag, the browser will
navigate to the address in the `href` attribute.

{{% notice blue Note "rocket" %}}
The DOM defines *numerous* events. Each element type does
NOT support every event type. The kinds of events that each element supports 
relate to how the element is used.
{{% /notice %}}

## Handling Events

Feature-rich web applications rely on more than the default event handling provided by the
DOM. We can add custom interactivity with the users by attaching event handlers to HTML
elements and then writing the event handler code.

To write a handler, you need to tell the browser what to do when a certain event happens.
DOM elements use the *on event* naming convention when declaring event handlers.

The first way we will handle events is to declare the event handler in HTML, this is often
referred to as an **inline event handler**. For example, when defining what happens 
when a `button` element is clicked, the `onclick` attribute is used. This naming 
convention can be read as: *On click of the button, print a message to the console.*

{{% notice blue Example "rocket" %}}
```html
<!DOCTYPE html>
<html>
<head>
    <title>Button click handler</title>
</head>
<body>
    <button onclick="console.log('you rang...');">Ring Bell</button>
</body>
</html>
```

**Console Output** (if button is clicked)

```console
you rang...
```
{{% /notice %}}

{{% notice green Tip "rocket" %}}
Notice the use of single quotes around `'you rang...'`. When declaring the value
of an attribute to be a string, you must use single quotes `'` inside the double
quotes `"`.
{{% /notice %}}

{{% notice blue Note "rocket" %}}
`button` elements represent a clickable entity. `button` elements have
default *click* handling behavior related to `form` elements. That we will
get into in a later chapter. For now, we will be defining the *click* handler 
behavior.
{{% /notice %}}

Any JavaScript function can be used as the event handler. That means any defined functions can be used. Because programmers can write functions to do whatever their hearts desire, defined functions as event handlers allow for more functionality to occur when an event is handled.

{{% notice blue Example "rocket" %}}
A function `youRang()` is defined and used as the event handler for when the button is clicked.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Button click handler</title>
    <script>
        function youRang() {
            document.getElementById("main-text").innerHTML += "you rang...";
            console.log("you rang...");
        }
    </script>
</head>
<body>
    <h1>demo header</h1>
    <p id="main-text" class="orange" style="font-weight: bold;">
        a bunch of really valuable text...
    </p>
    <button onclick="youRang();">Ring Bell</button>
</body>
</html>
```

**Result** (if button is clicked)

```console
effect on page: adds "you rang..." to <p>
output in console: you rang...
```
{{% /notice %}}

{{% notice orange Warning "rocket" %}}
When defining handlers via HTML, be very careful to type the function name correctly.
If the function name is incorrect, the event will not be handled. No warning is given,
the event is silently ignored.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What does an *event* represent in the browser JavaScript environment?
{{% /notice %}}

{{% notice green Question "rocket" %}}
Why is JavaScript considered an *event-driven* language?
{{% /notice %}}

{{% notice green Question "rocket" %}}
Receiving an event and responding to it is known as?

1. Holding an event
1. Having an event
1. Handling an event
{{% /notice %}}