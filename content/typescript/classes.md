# Classes and Interfaces in TypeScript

## Classes

Classes in TypeScript look something like this:

``` {.js linenos=""}
class Astronaut {
   name: string;
   constructor(firstName: string, lastName: string) {
      this.name = firstName + " " + lastName;
   }
   greet() {
      return "Hello, " + this.name;
   }
}

let Bob = new Astronaut("Bob","Smith");
```

You may remember the `this` and `new` keywords from working with classes
in JavaScript. Earlier in the chapter, we also noted that when declaring
variables in TypeScript, we have to specify the type of value. The same
applies to function parameters, as you can see in the constructor.

When `using inheritance <inheritance>`{.interpreted-text role="ref"},
classes in TypeScript can also use the `extends` keyword to denote child
and parent classes, as shown here:

``` {.js linenos=""}
class Panthera {
   roar: string;
   constructor(currentRoar: string) {
      this.roar = currentRoar;
   }
}

class Tiger extends Panthera {
   stripes: boolean = true;

}

let tigger = new Tiger("loud");
console.log(tigger.roar);
console.log(tigger.stripes);
```

## Interfaces

Interfaces are not used in JavaScript, but are important in TypeScript.
Like classes, interfaces define properties and methods that a type will
have. The difference is that interfaces do NOT include initialization of
properties or implementations of methods.

::: note
::: title
Note
:::

Though the use of interfaces in Angular is not within the scope of this
book, interfaces are used rather frequently in Angular code and are
important in object-oriented programming languages, such as Java.
:::

We may create an interface for a data type that contains all of the
information we need about an astronaut and then use that information in
a function.

``` {.js linenos=""}
interface Astronaut {
   name: string;
}

function astronautName (astronaut: Astronaut): string {
   return astronaut.name;
}

let bob = {name: "Bob"};
console.log(astronautName(bob));
```

Interfaces define the contract that other classes or objects must comply
with if implementing that interface. Multiple classes can implement one
interface, and that flexibility allows different classes to share one
type. This can be helpful when a function parameter needs to make use of
certain behaviors.

``` {.js linenos=""}
interface interfaceName {
   someProperty: number;
}

class className implements interfaceName {
   constructor(x: number) {
      this.someProperty = x;
   }
}
```

::: admonition
Example

``` {.js linenos=""}
interface Panthera {
   roar: string;
}

class Tiger implements Panthera {
   roar: string;

   constructor() {
      this.roar = 'rooooaaaarrrr';
   }
}

class Lion implements Panthera {
   roar: string;

   constructor() {
      this.roar = 'ROOOOAAAAARRRRRR';
   }
}

function pantheraSounds(panthera: Panthera): void {
   console.log(`Panthera says ${panthera.roar}`);
}

let tiger = new Tiger();
let lion = new Lion();

pantheraSounds(tiger);
pantheraSounds(lion);
```

In this example, the `Panthera` interface defines the `roar` property.
`Tiger` and `Lion` implement the `Panthera` interface, which means
`Tiger` and `Lion` must have a `roar` property.

The function `pantheraSounds` has one parameter of type `Panthera`. The
variables `tiger` and `lion` can be passed into `pantheraSounds` because
they are instances of classes that implement the `Panthera` interface.
:::

### Optional Parameters

`null` and `undefined` are primitive data types in TypeScript, however,
they are treated differently by TypeScript. If you are planning on using
`null` to define a property of an interface that is not known yet, use
the TypeScript optional parameter, `?`.

Let\'s take a look at how that would look in TypeScript.

In JavaScript, we might have an object that looks like so:

``` {.js linenos=""}
let giraffeTwo = {
     species: "Reticulated Giraffe",
     name: "Alicia",
     weight: null,
     age: 10,
     diet: "leaves"
};
```

If we wanted to declare the same object as an interface in TypeScript,
we would have to use the optional parameter for the `weight` property.

``` {.js linenos=""}
interface giraffeTwo = {
     species: string;
     name: string;
     weight?: number;
     age: number;
     diet: string;
};
```

## `export`

In TypeScript, you can use the `export` keyword to make classes and
interfaces available for import in other files. This will look familiar
to you as you saw something similar with
`modules <exporting-modules>`{.interpreted-text role="ref"}.

Using the `export` keyword looks something like this:

``` {.js linenos=""}
export class className {
   // properties and methods
}
```

## `import`

In TypeScript, you can use the `import` keyword to use classes and
interfaces declared in other files available for use in the file you are
working on. This is a similar idea to
`importing modules <require-modules>`{.interpreted-text role="ref"},
however, the syntax is different in TypeScript:

``` {.js linenos=""}
import { className } from 'relativefilepath';

let newClass = new className;
```

## Check Your Understanding

::: admonition
Question

What is the difference between a class and an interface?
:::
