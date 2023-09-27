---
title: "Declaring and Calling a Class"
date: 2023-09-15T16:20:48-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Creating a Class

Just like the `function` keyword defines a new function, the keyword for
defining a new class is `class`. By convention, class names start with
capital letters to distinguish them from JavaScript function and variable names
(e.g. `MyClass` vs. `myFunction`).

Remember that classes are blueprints for building multiple objects of the same
type. The general format for declaring a class is:

```js {linenos=table}
class ClassName {
   constructor(parameters) {
      //assign properties
   }
   //define methods
}
```

Note the keyword `constructor`. This is a special method for creating objects
of the same type, and it assigns the key/value pairs. Parameters are passed
into `constructor` rather than the `class` declaration.

### Assigning Properties

Let's set up an `Astronaut` class to help us store data about our animal
crew. Each animal has a `name`, `age`, and `mass`, and we assign these
properties in `constructor` as follows:

```js {linenos=table}
class Astronaut {
   constructor(name, age, mass) {
      this.name = name;
      this.age = age;
      this.mass = mass;
   }
}
```

The `this` keyword defines a key/value pair, where the text attached to
`this` becomes the key, and the value follows the equal sign (`this.key =
value`).

`constructor` uses the three `this` statements (`this.name = name`, etc.)
to achieve the same result as the object declaration
`let objectName = {name: someString, age: someNumber, mass: someMass}`. Each
time the `Astronaut` class is called, `constructor` builds an object with
the SAME set of keys, but it assigns different values to the keys based on the
arguments.

{{% notice blue "Note" "rocket" %}}

Each class requires *one* `constructor`. Including more than one
`constructor` results in a syntax error. If `constructor` is left out of
a class declaration, JavaScript adds an empty `constructor () {}`
automatically.

{{% /notice %}}

## Creating a New Class Object

To create an object from a class, we use the keyword `new`. The syntax is:

```js
let objectName = new ClassName(arguments);
```

`new` creates an **instance** of the class, which means that the object
generated shares the same set of keys as every other object made from the
class. However, the values assigned to each key may differ.

{{% notice blue "Example" "rocket" %}}

Let's create objects for two of our crew members: Fox and Hippo.

```js {linenos=table}
class Astronaut {
   constructor(name, age, mass){
      this.name = name;
      this.age = age;
      this.mass = mass;
   }
}

let fox = new Astronaut('Fox', 7, 12);
let hippo = new Astronaut('Hippo', 25, 1500);

console.log(typeof hippo, typeof fox);

console.log(hippo, fox);
```

**Console Output**

```console
object object

Astronaut { name: 'Hippo', age: 25, mass: 1500 }
Astronaut { name: 'Fox', age: 7, mass: 12 }
```

{{% /notice %}}

In lines 9 and 10, we call the `Astronaut` class twice and pass in different
sets of arguments, creating the `fox` and `hippo` objects.

The output of line 14 shows that `fox` and `hippo` are both the same
*type* of object (`Astronaut`). The two share the same *keys*, but they have
different values assigned to those keys.

{{% notice blue "Note" "rocket" %}}

Two objects created from the same class are NOT equal, even if the keys
within the objects all have the same values. The reason behind this was
discussed previously.

{{% /notice %}}

After creating an `Astronaut` object, we can access, modify, or add new
key/value pairs as described in the Objects and Math chapter.

{{% notice blue "Example" "rocket" %}}

Play around with modifying and adding properties inside and outside of the
`class` declaration. Open up `ClassExamples01.js` in `javascript-projects/classes/chapter-examples` to get started.

```js {linenos=true}
class Astronaut {
   constructor(name, age, mass){
      this.name = name;
      this.age = age;
      this.mass = mass;
   }
}

let fox = new Astronaut('Fox', 7, 12);

console.log(fox);
console.log(fox.age, fox.color);

fox.age = 9;
fox.color = 'red';

console.log(fox);
console.log(fox.age, fox.color);
```

**Console Output**

```console
Astronaut { name: 'Fox', age: 7, mass: 12 }
7 undefined
Astronaut { name: 'Fox', age: 9, mass: 12, color: 'red' }
9 'red'
```

{{% /notice %}}

Attempting to print `fox.color` in line 12 returns `undefined`, since that
property is not included in the `Astronaut` class. Line 15 adds the `color`
property to the `fox` object, but this change will not affect any other
objects created with `Astronaut`.

### Setting Default Values

What happens if we create a new `Astronaut` without passing in all of the
required arguments?

{{% notice blue "Example" "rocket" %}}

Open `ClassExamples02.js` in `javascript-projects/classes/chapter-examples` to explore what happens when we are missing some of the required arguments.

```js {linenos=table}
class Astronaut {
   constructor(name, age, mass){
      this.name = name;
      this.age = age;
      this.mass = mass;
   }
}

let tortoise = new Astronaut('Speedy', 120);

console.log(tortoise.name, tortoise.age, tortoise.mass);
```

{{% /notice %}}

To avoid issues with missing arguments, we can set a *default* value for a
parameter as follows:

```js {linenos=table}
class Astronaut {
   constructor(name, age, mass = 54){
      this.name = name;
      this.age = age;
      this.mass = mass;
   }
}
```

Now if we call `Astronaut` but do not specify a mass value, the constructor
automatically assigns a value of `54`. If an argument is included for
`mass`, then the default value is ignored.

TRY IT! Return to the code in the example above and set default values for
one or more of the parameters.

## Check Your Understanding

The questions below refer to a class called `Car`.

```js {linenos=table}
class Car {
   constructor(make, model, year, color, mpg){
      this.make = make;
      this.model = model;
      this.year = year;
      this.color = color;
      this.mpg = mpg;
   }
}
```

{{% notice green "Question" "rocket" %}}

If we call the class with `let myCar = new Car('Chevy', 'Astro', 1985,
'gray', 20)`, what is output by `console.log(typeof myCar.year)`?

1. object
1. string
1. function
1. number
1. property

{{% /notice %}}

<!-- number -->

{{% notice green "Question" "rocket" %}}

If we call the class with `let myCar = new Car('Tesla', 'Model S', 2019)`,
what is output by `console.log(myCar)`?

1. Car {make: 'Tesla', model: 'Model S', year: 2019, color: undefined, mpg: undefined }
1. Car {make: 'Tesla', model: 'Model S', year: 2019, color: '', mpg: '' }
1. Car {make: 'Tesla', model: 'Model S', year: 2019 }

{{% /notice %}}

