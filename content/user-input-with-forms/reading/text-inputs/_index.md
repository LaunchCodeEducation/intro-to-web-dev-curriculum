---
title: "Text Inputs"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 4
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

As you know from interacting with web forms, it's possible to use more than simple text
inputs. There are additional input *types*, each with different uses. Many of
the elements are `<input>` tags with a different `type` value, however some have
entirely different tag names. The next few sections contain lists of input types.

To start, here are three types of text inputs. These input types can contain text of any value.

| Type     | Syntax | Description | Demo |
|----------|--------|-------------|------|
| text     | `<input type="text" name="username"/>` | A single line text field. | {{< rawhtml >}}
<input type="text" name="username"/>
{{< /rawhtml >}} |
| textarea | `<textarea name="missionDescription"></textarea>` | A larger, multi-line text box. Must have open and closing tags. | {{< rawhtml >}}
<textarea name="missionDescription"></textarea>
{{< /rawhtml >}} |
| password | `<input type="password" name="passCode"/>`  | A text field that obscures the text typed by the user. | {{< rawhtml >}}
<input type="password" name="passCode"/>
{{< /rawhtml >}} |

{{% notice blue Note "rocket"%}}
Form inputs will NOT look exactly the same in all browsers.
However, the inputs *should* function the same way. Use [caniuse.com](https://caniuse.com),
if there is ever a question of browser support for a certain feature.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```html
<form action="https://handlers.education.launchcode.org/request-parrot" method="post">
    <label>Code Name<input type="text" name="codeName"/></label>
    <label>Code Word<input type="password" name="codeWord"/></label>

    <!-- textarea must have open and closing tags -->
    <label>Mission Description<br/>
    <textarea name="description" rows="5" cols="75"></textarea>
    </label>

    <button>Send Report</button>
</form>
```

![Form with Code Name, COde WOrd, and Description field. All fields have values.](pictures/basic-inputs-example.png?classes=border)

**Submitted Values**

```console
codeName=Captain+Danvers
codeWord=avengers!
description=Test+flight.+Plane+maintenance.+Superhero+stuff.

Notice that the textarea value does NOT include new lines, even though it was typed that way.
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which input type should be used if the user is going to enter a large amount of text?
{{% /notice %}}