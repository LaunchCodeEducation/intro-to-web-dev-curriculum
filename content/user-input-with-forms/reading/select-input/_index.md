---
title: "Select Input"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 8
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Select inputs create a clickable menu that displays options and allows the user
to select one. The available options are defined by `<option>` tags inside of
the `<select></select>` tag.

`<option>` tags have a `value` attribute which defines the value submitted
if that option is selected. The text inside the
`<option>Option text</option>` is what is displayed in the select menu.

| Type   | Syntax      | Description      | Demo    |
|--------|--------------|------------------|--------|
| select | `<select name="weather"><option value="1">clear</option><option value="2">cloudy</option></select>` | A menu that allows selection of one option. Requires options to be in `<option>` tags. | {{< rawhtml >}}<select name="weather"><option value="1">clear</option><option value="2">cloudy</option></select>{{< /rawhtml >}} |


{{% notice blue Example "rocket" %}}
```html
<form action="https://handlers.education.launchcode.org/request-parrot" method="post">
    <label>Operation Code:
    <!-- includes empty value "Select One" option -->
    <select name="operation">
    <option value="">* Select One *</option>
    <option value="1">Simulation</option>
    <option value="2">Rocket Test</option>
    <option value="3">Crew Related</option>
    </select>
    </label>

    <label>Facility:
    <select name="facility">
    <option value="johnson">Johnson Space Center, TX</option>
    <option value="kennedy">Kennedy Space Center, FL</option>
    <option value="white-sands">White Sands Test Facility, NM</option>
    </select>
    </label>
    <button>Send Report</button>
</form>
```

**Default Form Values**

![Web form showing select inputs for Operation Code and Facility](pictures/select-inputs-example1.png?classes=border)

**Select "Rocket Test" and "White Sands Test Facility, NM"**

![Web form with select inputs with "Rocket Test" and "White Sands Test Facility, NM" selected](pictures/select-inputs-example2.png?classes=border)

**Submitted Values**

```console
operation=2
facility=white-sands 
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
For a select input, what determines the value that is submitted during form submission?
{{% /notice %}}