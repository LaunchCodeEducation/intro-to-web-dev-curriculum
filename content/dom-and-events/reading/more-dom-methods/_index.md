---
title: "More DOM Methods and Properties"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

The following sections are a summary of some DOM classes, methods, and properties. A
more complete list can be found in the reference links below. You do NOT need to memorize everything on these reference pages.
We are providing them to you as a guide for your future studies of the DOM.

1. [W3Schools DOM reference](https://www.w3schools.com/js/js_htmldom_document.asp).
2. [MDN DOM reference](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction#Important_Data_Types).

## Window

The global variable `window` is an instance of the `Window` class. The `Window` class represents the browser
window. In the case of multi-tabbed browsers, the global `window` variable represents the specific tab in which
the JavaScript code is running.

| Method or Property              | Syntax                                 | Description                                                                       |
|--------------------------------|----------------------------------------|-----------------------------------------------------------------------------------|
| alert                          | `window.alert("String message")`      | Displays a dialog box with a message and an "ok" button to close the box.          |
| [confirm](#dom-confirm-examples) | `window.confirm("String message")`    | Displays a dialog box with a message and returns `true` if the user clicks "ok" and `false` if the user clicks "cancel". |
| location                       | `window.location`                      | Object that represents and alters the web address of the window or tab.         |
| console                        | `window.console`                       | Represents the debugging console. Most common and basic use is `window.console.log()`. |

{{% notice blue Note "rocket" %}}
When using JavaScript in the browser environment, methods and properties defined on the `Window`
class are exposed as global functions and variables. An example of this is `window.console.log()`
is accessible by referencing `console.log()` directly.
{{% /notice %}}

## Document

The global `document` variable is an instance of the `Document` class. The `Document` class represents the
HTML web page that is read and displayed by the browser. The `Document` class provides properties and methods
to find, add, remove, and alter HTML elements inside on the web page.

| Method or Property                   | Syntax                                     | Description                                                |
|-------------------------------------|--------------------------------------------|------------------------------------------------------------|
| title                               | `document.title`                            | Read or set the title of the document.                    |
| [getElementById](#dom-getElementById-examples) | `document.getElementById("example-id")`   | Returns a reference to the element whose `id` attribute matches the given string value. |
| [querySelector](#dom-querySelector-examples)   | `document.querySelector("css selector")`   | Returns the first element that matches the given CSS selector. |
| [querySelectorAll](#dom-querySelectorAll-examples) | `document.querySelectorAll("css selector")` | Returns a list of elements that match the given CSS selector. |

{{% notice blue Note "rocket" %}}
`querySelector` and `querySelectorAll` use the CSS selector pattern to find matching elements. The pattern
passed in must be a valid CSS selector. Elements will be found and returned the same way that elements
are selected to have CSS rules applied.
{{% /notice %}}



## Element

HTML documents are made up of a tree of elements. The `Element` class represents an HTML element.

| Method or Property              | Syntax                              | Description                                   |
|--------------------------------|-------------------------------------|-----------------------------------------------|
| getAttribute                    | `element.getAttribute("id")`        | Returns the value of the attribute.          |
| setAttribute                    | `element.setAttribute("id", "string-value")` | Sets the attribute to the given value. |
| [style](#dom-style-object-examples) | `element.style.color`               | Object that allows reading and setting *INLINE* CSS properties. |
| [innerHTML](#dom-innerHTML-examples) | `element.innerHTML`                 | Reads or sets the HTML inside an element.    |


## Check Your Understanding

{{% notice green Question "rocket" %}}
What value will `response` have if the user clicks *Cancel*?

```javascript
let response = window.confirm("String message");
```
{{% /notice %}}

{{% notice green Question "rocket" %}}
Which of these are TRUE about selecting DOM elements?

1. You can select elements by *CSS class* name
1. You can select elements by *id attribute* value
1. You can select elements by *tag* name
1. All of the above
{{% /notice %}}