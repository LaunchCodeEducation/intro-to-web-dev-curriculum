---
title: "Checkbox Input"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 6
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

A checkbox input represents a box to check. Checkbox inputs can be
used by themselves or in groups. Checkbox inputs are best used with `<label>` tags.

| Type     | Syntax                                       | Description                                  | Demo                                              |
|----------|----------------------------------------------|----------------------------------------------|---------------------------------------------------|
| checkbox | `<input type="checkbox" name="signUp"/>`    | A small box for marking form option as *checked*. | {{< rawhtml >}}<label>sign up<input type="checkbox" name="signUp"/></label>{{< /rawhtml >}} |


## Examples

{{% notice blue Example "rocket" %}}
One checkbox. No `value` attribute is set, so the default value of `on` is submitted.

```html
<label>crew<input type="checkbox" name="crewReady"/></label>
```

**Submitted** (if checked)

```console
crewReady=on
```
{{% /notice %}}

{{% notice blue Example "rocket" %}}
Multiple checkbox inputs. All with *different* `name` attributes.

```html
<div>Activities</div>
<label>cooking<input type="checkbox" name="cooking"/></label>
<label>running<input type="checkbox" name="running"/></label>
<label>movies<input type="checkbox" name="movies"/></label>
```

**Submitted** (if cooking and movies are checked)

```console
cooking=on&movies=on
```
{{% /notice %}}

{{% notice blue Example "rocket" %}}
Multiple checkbox inputs with the SAME `name` attribute.

```html
<div>Ingredients</div>
<label>Onion<input type="checkbox" name="ingredient" value="onion"/></label>
<label>Butter<input type="checkbox" name="ingredient" value="butter"/></label>
<label>Rice<input type="checkbox" name="ingredient" value="rice"/></label>
```

**Submitted** (if butter and rice are checked)

```console
ingredient=butter&ingredient=rice
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is the default value submitted for a `<checkbox>` when checked?
{{% /notice %}}