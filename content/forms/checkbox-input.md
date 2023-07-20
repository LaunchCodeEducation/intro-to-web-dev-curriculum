# Checkbox Input

A checkbox input represents a box to check. Checkbox inputs can be used
by themselves or in groups. Checkbox inputs are best used with `<label>`
tags.

  Type       Syntax                                     Description                                         Demo
  ---------- ------------------------------------------ --------------------------------------------------- -----------------------------------------------------------------------
  checkbox   `<input type="checkbox" name="signUp"/>`   A small box for marking form option as *checked*.   `<label>sign up<input type="checkbox" name="signUp"/></label>`{=html}

## Examples

::: admonition
Example

One checkbox. No `value` attribute is set, so the default value of `on`
is submitted.

``` html
<label>crew<input type="checkbox" name="crewReady"/></label>
```

**Submitted** (if checked)

    crewReady=on

[Run it at repl.it](https://repl.it/@launchcode/checkbox-inputs-example)
:::

::: admonition
Example

Multiple checkbox inputs. All with *different* `name` attributes.

``` html
<div>Activities</div>
<label>cooking<input type="checkbox" name="cooking"/></label>
<label>running<input type="checkbox" name="running"/></label>
<label>movies<input type="checkbox" name="movies"/></label>
```

**Submitted** (if cooking and movies are checked)

    cooking=on&movies=on

[Run it](https://repl.it/@launchcode/checkbox-inputs-example)
:::

::: admonition
Example

Multiple checkbox inputs with the SAME `name` attribute.

``` html
<div>Ingredients</div>
<label>Onion<input type="checkbox" name="ingredient" value="onion"/></label>
<label>Butter<input type="checkbox" name="ingredient" value="butter"/></label>
<label>Rice<input type="checkbox" name="ingredient" value="rice"/></label>
```

**Submitted** (if butter and rice are checked)

    ingredient=butter&ingredient=rice

[Run it](https://repl.it/@launchcode/checkbox-inputs-example)
:::

## Check Your Understanding

::: admonition
Question

What is the default value submitted for a `<checkbox>` when checked?
:::
