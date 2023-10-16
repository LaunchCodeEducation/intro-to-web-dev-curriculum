---
title: "Asynchronous and Promises"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewesr
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In order to fully explain how the `fetch` function works, we need to define
and talk about the terms **asynchronous** and **synchronous**.

> Asynchronous: Not simultaneous or concurrent in time.

> Synchronous: Simultaneous or concurrent in time.

When fetching data in JavaScript, the HTTP requests are asynchronous. In brief, that
means when an HTTP request is sent, we don't know exactly when a response will be
received by the browser. Remember that HTTP requests are sent to an address, then a
response is sent. That process takes a variable amount of time depending on network
speed, the address location, and response size.

{{% notice blue Note "rocket" %}}
These requests are also called **AJAX requests** (Asynchronous JavaScript and XML).
The XML part of AJAX refers to a data format that was popular before JSON.
{{% /notice %}}

## Response Handlers

Browsers can't stop everything and wait for a response to an HTTP request. Browsers
have to render HTML, interact with the user, and run JavaScript. To keep these
processes running seamlessly, without any noticeable pauses, the browser relies on
events.

This is where `.then()` and the response handler function come in. The browser
provides us with a way to handle the response whenever it is received.


## Promises and the `then` Function

Let's look again at a simple `fetch` example. Notice on line 1 that `then` is
called on the value returned from `fetch`.

```javascript
fetch("https://handlers.education.launchcode.org/static/weather.json").then( function(response) {
    console.log(response);
} );
```

To make it clearer, let's capture the value returned by `fetch` in a variable
named `fetchPromise`.

```javascript
const fetchPromise = fetch("https://handlers.education.launchcode.org/static/weather.json");
fetchPromise.then( function(response) {
    console.log(response);
} );
```

`fetch` returns an instance of the `Promise` class. The `Promise` class
represents a **promise**. A promise is the `eventual` outcome of an asynchronous event.
In the above example, ``fetchPromise`` represents the eventual response from the HTTP request to
`https://handlers.education.launchcode.org/static/weather.json`.

A promise can be fulfilled or rejected. When a promise is fulfilled, data is passed
to the response handler function. The `then` method of `Promise` defines what will
happen when the promise is fulfilled. When a promise is rejected, the error reason is
returned.

The above example can be translated to these steps

1. Make an HTTP request to `https://handlers.education.launchcode.org/static/weather.json`
1. When the response is received, THEN run the response handler function (passing in response data)
1. In the response handler function, console log the `response` object

## More Promises

Above, we showed a promise representing the outcome of an HTTP request, however, promises can represent the outcome of `any` asynchronous event.
For example, the ``response`` object has a `json()` function that will return the JSON data in the
response. The `json()` function returns a `promise` that represents the future result
of turning the response data into JSON.

The example below shows how promises are used to represent two different types of asynchronous events and the outcomes.

{{% notice blue Example "rocket" %}}
```javascript
const fetchPromise = fetch("https://handlers.education.launchcode.org/static/weather.json");
fetchPromise.then( function(response) {
    const jsonPromise = response.json();
    jsonPromise.then( function(json) {
    console.log("temp", json.temp);
    });
} );
```

This example involves two promises. On line 1, `fetchPromise` is a promise that represents the
fetch request. On line 3, `jsonPromise` is a promise that represents the response data being turned
into JSON.

Finally on line 5, the JSON data can be logged.
{{% /notice %}}

{{% notice green Tip "rocket" %}}
Promises can be a hard concept to understand. Focus on the examples and the theory will
make sense in time.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
We know exactly when an asynchronous request will return.

1. True
1. False
<!-- Solution: False -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
A promise can represent the outcome of *any* future event.

1. True
1. False

<!-- Solution: True -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
`then` is a method of the `Promise` class that allows us to run code
after an event is completed.

1. True
1. False

<!-- Solution: True -->
{{% /notice %}}