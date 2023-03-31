---
title: "The JavaScript-y Way"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 1
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

So far, we have been learning **Vanilla JavaScript** or **VanillaJS**. VanillaJS is a term used to describe plain JavaSript that doesn't employ any additional libraries or frameworks. Learning about programming and web development using VanillaJS is extremely useful in understanding the underlying behaviors of those frameworks and why programmers use them. 

VanillaJS is more formally referred to **ECMAScript**. When **ECMAScript2015** or **ES6** was released, several key features were introduced that allow React developers to write more efficient code. We encountered these terms earlier when learning about template literals. We have introduced coding concepts to you using JavaScript syntax that is close to other languages, but ES6 has some specialized syntax that you are likely to see in more complex JavaScript applications. 

{{% notice blue "Note" "rocket" %}}
   There are many different versions of ECMAScript. At the time of writing in March 2023, we are focusing on ES6, because the ES6 release featured many groundbreaking changes and had widespread browser support across different browsers and browser versions.
{{% /notice %}}

## Arrow Functions

So far we have seen functions and we also learned about anonymous functions. Another way to write a function with ES6 is to write an **arrow function**. Using arrow functions will make your code more compact. In general, an arrow function looks like so:

```js 
   functionName = (parameters) => {
      // function body
   }
```

{{% notice blue "Note" "rocket" %}}
   Due to the syntactical structure of arrow functions, arrow functions are also anonymous functions.
{{% /notice %}}

For example, let's write a function for a hiking application. If a hiker wants to log a hike they just went on, we should add the number of miles they hiked to a lifetime total. Being expert JavaScript developers, we are going to write a function that will add the two numbers together. Before trying out arrow functions, let's write a function that accomplishes this task.

```js
   addLatestHike = function(miles, lifetimeTotal) {
      return lifetimeTotal + miles;
   }
```

Now we want to rewrite `addLatestHike()` and turn it into an arrow function.

```js
   addLatestHike = (miles, lifetimeTotal) => {
      return lifetimeTotal + miles;
   }
```

Now, one of the advantages of using arrow functions is that we can make our code more compact. We can simplify the above function even further because it only has *one* statement in the function body and that is the `return` statement. The equivalent and more compact way to write `addLatestHike()` is:

```js
   addLatestHike = (miles, lifetimeTotal) => lifetimeTotal + miles;
```

{{% notice blue "Note" "rocket" %}}
   If you have exactly one parameter, you do not have to wrap that parameter in parantheses. Let's say `lifetimeTotal` was actually a global constant and we were writing a function that would return the sum of `lifetimeTotal` and a singular parameter, `miles`. Then our `addLatestHike()` function would actually be:

   ```js
      addLatestHike = miles => lifetimeTotal + miles;
   ```

{{% /notice %}}

There are many advantages of using arrow functions, but you should NOT use arrow functions as class constructors or class methods. Arrow functions treat the `this` keyword differently than regular functions. With a regular function, the `this` keyword refers to the object that calls the function so we can use it when writing class methods. With an arrow function, the `this` keyword refers to the object that owns the function so we would not get the same result if we use it in a class method. Furthermore, when writing ES6 classes, the use of `=` in our function declaration will designate our method as a property. Unlike methods, properties are not shared by instances of classes and instead are generated with each instance. This may not seem worrisome if we only have one class with three instances, but if we scale our application up to one class with 1,000,000 instances, all of those arrow functions that are now properties will slow our application down. Just because something is technically possible doesn't mean that it is advisable when it comes to scalability.

## The Spread Operator

Another new syntatical expression you may see when you start diving in to more complex applications is the **spread operator**. The spread operator is written as three periods and appears before the object that you want to apply it to. We can use this operator whenever we want to expand an iterable and access all of it's elements, such as passing each object in the iterable to a function as arguments or applying an operation to each object in an iterable. We can use the spread operator to make a copy of an array easily since it allows the computer to expand the iterable and access the individual elements. Here is how we write the code when we want to make a copy of an array:

```js
let array1 = ["STL", "KC", "Philly"];
let array2 = [...array1];
```

Now `array2` contains all three elements of `array1` in the same order so we could add another element to `array2` without impacting `array1`. 

We can make use of the spread operator in our hiking application. First, let's take a look at some of the code our colleagues wrote. Their code contains two functions: `findWeeklyTotal()` and `addWeeklyTotal()`. `findWeeklyTotal()` returns the total for miles hiked in a week. `addWeeklyTotal()` returns the sum of the miles hiked in a week and that hiker's `lifetimeTotal`.  

```js {linenos = table}
   let lifetimeTotal = 0;
   let weeklyTotal = 0;

   findWeeklyTotal = (m, t, w, th, f, sa, su) => {
      weeklyTotal = m + t + w + th + f + sa + su;
   }

   addWeeklyTotal = () => {
      lifetimeMiles = lifetimeMiles + weeklyTotal;
      weeklyTotal = 0;
   }
```

Now each user's logged miles for hikes are saved in arrays for each week. The miles hiked on Monday is stored at index 0, the miles hiked on Tuesday at index 1, and so on. If the hiker didn't log a hike, then the value stored is just 0. If a hiker goes on two hikes in a week, one on Tuesday that was 2.1 miles and one on Saturday that was 5.3 miles, then `milesHikedThisWeek` would be `[0, 2.1, 0, 0, 0, 5.3, 0]`. Let's take a look at what the code looks like when our user, Judy, goes on a hike every day of the week and each hike is 5.0 miles long. We can use the spread operator to pass our array to `findWeeklyTotal()` like so:

```js {linenos = table}
   let lifetimeMiles = 0;
   let weeklyTotal = 0;
   let milesHikedThisWeek = [5.0, 5.0, 5.0, 5.0, 5.0, 5.0, 5.0];

   findWeeklyTotal = (m, t, w, th, f, sa, su) => {
      weeklyTotal = m + t + w + th + f + sa + su;
   }

   addWeeklyTotal = () => {
      lifetimeMiles = lifetimeMiles + weeklyTotal;
      weeklyTotal = 0;
   }

   findWeeklyTotal(...milesHikedThisWeek);
   addWeeklyTotal();
```

This way we don't have to loop through `milesHikedThisWeek` to pass all seven values to `findWeeklyTotal()`. We can just use the spread operator!

{{% notice orange "Warning" "rocket" %}}
   You may be tempted to try and use the spread operator in function arguments, but doing so will make the item a rest parameter. To learn mroe about rest parameters and how they differ from the spread operator, check out this article from [freeCodeCamp](https://www.freecodecamp.org/news/javascript-rest-vs-spread-operators/).
{{% /notice %}}

## To `Map` or not to `map()`?

Finally, when working with React applications, you may see the word "map" a lot. This is because there is a function called `map()` and a collection called `Map`.

### `Map`

You may recall from learning about objects in JavaScript that objects are collections of key-value pairs where the keys are unordered and the collection is not iterable. **Maps**, on the other hand, are collections of key-value pairs where the keys are ordered and the collection is iterable. Also, you are not restricted to just using strings for your keys. You can use any primitive data type as a key with maps.

In our hiking application, we can turn our `milesHikedThisWeek` into a `Map`. Let's do so using Judy's data from the above example.

```js {linenos = table}
   let milesHikedThisWeek = new Map([
      ['Monday', 5.0],
      ['Tuesday', 5.0],
      ['Wednesday', 5.0],
      ['Thursday', 5.0],
      ['Friday', 5.0],
      ['Saturday', 5.0],
      ['Sunday', 5.0]
   ]);
```

Since the days of the week are in a specific order, it makes sense that we would want to use an ordered collection to store Judy's hiking data. The other benefit is that `milesHikedThisWeek` is iterable. To loop through a `Map`, we need to use a new style of loop called a **for/of loop**. 

```js {linenos = table}
   for (const [key, value] of milesHikedThisWeek) {
      console.log(`On ${key}, you hiked ${value} miles!`);
   }
```

With this code, we would get the following output.

```console
   On Monday, you hiked 5.0 miles!
   On Tuesday, you hiked 5.0 miles!
   On Wednesday, you hiked 5.0 miles!
   On Thursday, you hiked 5.0 miles!
   On Friday, you hiked 5.0 miles!
   On Saturday, you hiked 5.0 miles!
   On Sunday, you hiked 5.0 miles!
```
 
While there are many advantages to using `Maps`, keep in mind that if you are parsing JSON, you will need to use an object instead. JSON is an unordered collection so you cannot convert between JSON and `Maps`.

### `map()`

While a JavaScript `Map` is a type of collection, `map()` is an array method in JavaScript. `map()` is used in React applications to quickly display all the objects in an array. You can also use `map()` to create a copy of an array and apply a function to each item in the array.

## Check Your Understanding

{{% notice green "Question" "rocket" %}}
   Arrow functions are also _______ functions.

   1. anonymous
   1. odd
   1. class
   1. named

{{% /notice %}}

<!-- anonymous -->

{{% notice green "Question" "rocket" %}}

   What do you think `evenNumbers` will hold after this code executes?

   ```js
      let oddNumbers = [1, 3, 5];
      let evenNumbers = oddNumbers.map(number => number * 2);
   ```
{{% /notice %}}

<!-- it will probably hold [2,6,10] -->