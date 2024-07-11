---
title: "Radio Input"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 7
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Radio inputs allow a user to pick one option out of a grouping of options.
Radio inputs with the same name are grouped. Only one radio input in a group
can be chosen at a time. The `value` attribute of the chosen radio input will
be submitted. Radio inputs are best used with `<label>` tags.

| Type  | Syntax                                          | Description                                               | Demo                                              |
|-------|-------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------|
| radio | `<input type="radio" name="crewReady" value="yes"/>` | A small circle that allows selecting *one* of multiple values. Used in groups of two or more. | {{< rawhtml >}}<label>yes<input type="radio" name="crewReady" value="yes"/></label><label>no<input type="radio" name="crewReady" value="no"/></label>{{< /rawhtml >}} |

{{% notice blue Example "rocket" %}}
```html
<form action="https://handlers.launchcodelearning.org/request-parrot" method="post">
    Flight Rating:
    <label>Rough<input type="radio" name="flightRating" value="rough"/></label>
    <label>Few Bumps<input type="radio" name="flightRating" value="fewBumps"/></label>
    <label>Smooth<input type="radio" name="flightRating" value="smooth"/></label> 
    <button>Send Report</button>
</form>
```

![Form for flight rating, with a radio inputs for rough, few bumps, and smooth.](pictures/radio-inputs-example.png?classes=border)

**Submitted Values**

```console
flightRating=smooth
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Should a group of radio inputs have the same value for the `name` attribute?
{{% /notice %}}