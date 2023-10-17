---
title: "Specialized Text Inputs"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 5
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

For these text inputs the browser will validate and provide feedback to the user based on
rules for the declared type.

| Type  | Syntax  | Description    | Demo     |
|-------|-----|-------------------|--------|
| date  | `<input type="date" name="flightDate"/>`  | Browser validates the value is a valid date format. Some browsers provide a *date picker*. | {{< rawhtml >}}<input type="date" name="flightDate"/>{{< /rawhtml >}} |
| email | `<input type="email" name="emailAddress"/>` | Browser validates the value is a valid email address format. | {{< rawhtml >}}<input type="email" name="emailAddress"/>{{< /rawhtml >}} |
| number| `<input type="number" name="fuelTemp"/>` | Browser validates the value is a valid number format.   | {{< rawhtml >}}<input type="number" name="fuelTemp"/>{{< /rawhtml >}} |

{{% notice blue Example "rocket" %}}
```html
<form action="https://handlers.education.launchcode.org/request-parrot" method="post">
    <label>Email<input type="email" name="emailAddress"/></label>
    <label>Report Date<input type="date" name="reportDate"/></label>
    <label>Crew Count<input type="number"
    name="crewCount" min="1" max="10"/></label>
    <button>Send Report</button>
</form>
```

![Form with Code Name, Code Word, and Description field. All fields have values.](pictures/specialized-inputs-example.png?classes=border)

**Submitted Values**

```console
emailAddress=c.danvers@us.af.mil
reportDate=2019-03-08
crewCount=8
```
{{% /notice %}}