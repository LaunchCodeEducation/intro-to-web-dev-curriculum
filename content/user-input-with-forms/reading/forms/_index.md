---
title: "Forms"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

As a user of the web, you know that web pages both display and accept data. In this chapter
we are going to learn more about how web pages handle data input using HTML forms.
An HTML **form** is used to accept input from the user and send that data to the server.

## Create a Form

To declare a form in HTML use the `<form>` tag with open and closing tags. This form element
will serve as container for various types of other elements that are designed to capture
input from the user.

```html
<html>
    <head>
        <title>Form Example</title>
    </head>
    <body>
        <!-- empty form -->
        <form></form>
    </body>
</html>
```

An empty `<form></form>` will not appear on a web page until inputs have been
added inside of it. Below we have added one basic
`<input>` tag.

```html
<html>
    <head>
        <title>Form Example</title>
    </head>
    <body>
        <form>
        <input type="text"/>
        </form>
    </body>
</html>
```

## Input Element

The `input` element is used to add interactive fields, which allow the user to enter data.
`input` elements have two very important attributes: *name* and *type*.

- The `name` attribute is used to identify the input's value when the data is submitted
- The `type` attribute defines which type of value of the input represents

```html
<input type="text" name="username"/>
```

{{% notice blue Note "rocket" %}}
Notice that `<input type="text"/>` tags are self closing. **Self-closing** tags are *single* tags
with `/>` at the end.
{{% /notice %}}

{{% notice orange Warning "rocket" %}}
Values are NOT submitted for an `<input>` unless it has a `name` attribute.
{{% /notice %}}

## Labels

Forms normally contain more than one input. `<label>` tags are used to provide a textual
label, which informs the user of the purpose of the field. The simplest usage of
`<label>` tags is to *wrap* them around `<input>` tags.

```html
<html>
    <head>
        <title>Form Example</title>
    </head>
    <body>
        <form>
        <label>Username <input type="text" name="username"/></label>
        <label>Team Name <input type="text" name="team"/></label>
        </form>
    </body>
</html>
```

![HTML that includes a form tag with two input elements. Each element is inside of a label element.](pictures/label-example.png?classes=border)

A second way to relate a `<label>` tag to an `<input>` is to use the `id` attribute of
`input` and the `for` attribute of `label`. The two are related by setting `for` in `<label for="username">`
equal to the `id` of `<input id="username">`, these two attributes must be EQUAL.
When `for` is used, the `<input>` does NOT have to be inside of the `<label>`.

```html
<label for="username">Username</label>
<input id="username" name="username" type="text"/>
```

What happens when a `<label>` is clicked? The answer depends on what the `<label>` is
associated to.

For *text* inputs, when the label is clicked, then the input gains *focus*. An element with
**focus** is currently selected by the browser and ready to receive input.

{{% notice blue Example "rocket" %}}
Try clicking on the `Username` and `Team Name` labels below. What
happens?

```html
<form>
    <label>Username <input type="text" name="username"/></label>
    <label>Team Name <input type="text" name="team"/></label>
</form>
```
{{% /notice %}}

{{< rawhtml >}}
<form>
    <label>Username <input type="text" name="username"/></label>
    <label>Team Name <input type="text" name="team"/></label>
</form>
{{< /rawhtml >}}

For *non-text* inputs, when the label is clicked, a value is selected. This behavior
can be seen with `radio` and `checkbox` elements which we will learn more about soon.

{{% notice blue Example "rocket" %}}
Click on the label text to the associated checkbox input element to gain focus.

```html
<form>
    <label>Subscribe to Newsletter
    <input type="checkbox" name="newsletter"/>
    </label>
</form>
```
{{% /notice %}}

{{< rawhtml >}}
<form>
    <label>Subscribe to Newsletter
    <input type="checkbox" name="newsletter"/>
    </label>
</form>
{{< /rawhtml >}}

## Value Attribute

The `value` attribute of an `<input>` tag can be used to set the default value. If the
`value` attribute is declared, then the browser will show that value in the input. The user
can choose to update the value by typing in the input box.

{{% notice blue Example "rocket" %}}
Input with default value of JavaScript.

```html
<form>
    <label>Language <input name="language" type="text" value="JavaScript"/></label>
</form>
```
{{% /notice %}}

{{< rawhtml >}}
<form>
    <label>Language <input name="language" type="text" value="JavaScript"/></label>
</form>
{{< /rawhtml >}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is the purpose of the `name` attribute for `input` elements?
{{% /notice %}}

{{% notice green Question "rocket" %}}
Which `input` attribute sets the default value?
{{% /notice %}}