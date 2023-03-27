---
title: "The JavaScript-y Way"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 1
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

So far, we have been learning **Vanilla JavaScript** or **VanillaJS**. VanillaJS is a term used to describe plain JavaSript that doesn't employ any additional libraries or frameworks. Learning about programming and web development using VanillaJS is extremely useful in understanding the underlying behaviors of those frameworks and what they are trying to do. 

VanillaJS is more formally referred to **ECMAScript 2015** or **ES6**. We encountered these terms earlier when learning about template literals. We have introduced coding concepts to you using JavaScript syntax that is close to other languages, but ES6 has some specialized syntax that you are likely to see in more complex JavaScript applications. 

## Arrow Functions

We have seen functions in JavaScript before and we have seen anonymous functions. Arrow functions are more compact than traditional function syntax and are also anonymous. In general, an arrow function looks like so:

```js 
   functionName = (parameters) => {
      // function body
   }
```

Let's say that we want to write a function for a hiking application. We need a function that increases the miles traveled over a hiker's lifetime by the miles they just hiked. If we were NOT using arrow functions, we might write the following:

```js
   addLatestHike = function(miles, lifetimeTotal) {
      return lifetimeTotal + miles;
   }
```

To use arrow functions, we would write the same function as:

```js
   addLatestHike = (miles, lifetimeTotal) => {
      return lifetimeTotal + miles;
   }
```

Now, one of the advantages of using arrow functions is that we can make our code more compact. We can simplify the above function even further because it only has *one* statement and that is the `return` statement. The equivalent and more compact way to write `addLatestHike()` is:

```js
   addLatestHike = (miles, lifetimeTotal) => lifetimeTotal + miles;
```

{{% notice blue "Note" "rocket" %}}
   If you have exactly one parameter, you do not have to wrap that parameter in parantheses. Let's say `lifetimeTotal` was actually a global constant. Then our `addLatestHike()` function would actually be:

   ```js
      addLatestHike = miles => lifetimeTotal + miles;
   ```

{{% /notice %}}

There are many advantages of using arrow functions, but you need to be cognizant of a few things. First of all, arrow functions should not be used as constructors or class methods. Arrow functions treat the `this` keyword differently than regular functions. With a regular function, the `this` keyword refers to the object that calls the function. With an arrow function, the `this` keyword refers to the object that owns the function. Further more, when writing ES6 classes, the use of `=` in our function declaration will designate our method as a property. Properties are not shared by instances of classes and instead are generated with each instance. This may not seem worrisome if we only have one class with three instances, but if we scale our application up to one class with 1,000,000 instances, all of those arrow functions that are now properties will slow our application down. Just because something is technically possible doesn't mean that it is advisable when it comes to scalability.

## The Spread Operator

Another new syntax expression you may see when you start diving in to more complex applications is the **spread operator**. The spread operator is written as three periods and appears before the object that you want to apply it to. We can use this operator whenever we want to expand an iterable and access all of it's elements, such as passing each object in the iterable to a function as arguments. Here is how we write it when we want to make a copy of an array:

```js
let array1 = ["STL", "KC", "Philly"];
let array2 = [...array1];
```

Now `array2` contains all three elements of `array1` so we could add another element to `array2` without impacting `array1`. Let's try and use the spread operator in our hiking application. Now each user can log the miles hiked and if they go on more than 1, but less than 8 hikes in one week, those miles are saved as an array, `milesHikedThisWeek`. That array may vary in size depending on how many hikes the user went on that week. First, let's take a look at how some of the code may work that helps total up the miles hiked in one week and then add that total to the hiker's `lifetimeMiles`.

```js {linenos = table}
   let lifetimeMiles = 0;
   let weeklyTotal = 0;

   findWeeklyTotal = (m, t, w, th, f, sa, su) => {
      weeklyTotal = m + t + w + th + f + sa + su;
   }

   addWeeklyTotal = week => {
      lifetimeMiles = lifetimeMiles + weeklyTotal;
      weeklyTotal = 0;
   }
```

Now Judy is one of our users and she went on seven hikes this week and each hike was 5 miles long. We can use the spread operator to pass our array to `findWeeklyTotal()` like so:

```js {linenos = table}
   let lifetimeMiles = 0;
   let weeklyTotal = 0;
   let milesHikedThisWeek = [5, 5, 5, 5, 5, 5, 5];

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

## Map

Maps are collections of key-value pairs where the keys are intrinsically ordered and Maps are also iterable.
### For/of loop

