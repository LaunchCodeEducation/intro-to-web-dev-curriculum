---
title: "Exercises: More on Functions"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

Arrr! Welcome back, pirates. 

## Practice Your Skills

First, create an anonymous function and practice how to use the map method.

1. Create an anonymous function and set it equal to a variable. Your function should:

- If passed a number, return the tripled value.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let practice = function(myArg) {
      if (typeof myArg === "number") {
         return myArg * 3;
      }
   }
   ```
   {{% /expand %}}

- If passed a string, return the string "ARRR!"
- If NOT passed a number or string, return the data unchanged.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let practice = function(myArg) {
      if (typeof myArg === "number") {
         return myArg * 3;
      } else if (typeof myArg === "string") {
         return "ARRR!";
      } else {
         return myArg;
      }

   }
   ```
   {{% /expand %}}

2. Add to your code! Use your function and the [map method]({{< relref "../reading/pass-function-as-arguments/_index.md#example-the-array-method-map" >}}) to change the array `['Elocution', 21, 'Clean teeth', 100]` as follows:

- Triple all the numbers.
- Replace the strings with "ARRR!"
- Print the new array to confirm your work.

## Raid a Shuttle

You may still be wondering *Why would I ever use an anonymous
function?* For today's mission, of course! 

You need to hack into the shuttle code and steal supplies. Since the
LaunchCode TAs keep a sharp eye on the shuttle goodies, you can't just add new functions
like `siphonFuel` or `lootCargo`. You need to be more sneaky.

Clever.

Invisible.

*Anonymous*.

The first mate swiped a copy of the code you need to hack:

```javascript
function checkFuel(level) {
   if (level > 100000){
      return 'green';
   } else if (level > 50000){
      return 'yellow';
   } else {
      return 'red';
   }
}

function holdStatus(arr){
   if (arr.length < 7) {
      return `Spaces available: ${7 - arr.length}`;
   } else if (arr.length > 7){
      return `Over capacity by ${arr.length - 7} items.`
   } else {
      return "Full";
   }
}

let fuelLevel = 200000;
let cargoHold = ['meal kits', 'space suits', 'first-aid kit', 'satellite', 'gold', 'water', 'AE-35 unit'];

console.log("Fuel level: "+ checkFuel(fuelLevel));
console.log("Hold status: "+ holdStatus(cargoHold));
```

3. First, steal some fuel from the shuttle:

- Define an anonymous function and set it equal to a variable with a normal, non-suspicious name.  The function takes one parameter. This will be the fuel level on the shuttle.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let nonSuspiciousFunction = function(a) {

   }
   ```
   {{% /expand %}}

- You must siphon off fuel without alerting the TAs. Inside your function, you want to reduce the fuel level as much as possible WITHOUT changing the color returned by the `checkFuel` function.
- Once you figure out how much fuel to pump out, return that value.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let nonSuspiciousFunction = function(a) {
      if (checkFuel(a) === 'green') {
         return a - 100001;
      }
      else if (checkFuel(a) === 'yellow') {
         return a - 50001;
      }
      else {
         return a;
      }
   };
   ```
   {{% /expand %}}

- Decide where to best place your function call to gather our new fuel.
   
{{% notice green Tip "rocket" %}}
Be sure to test your function! Those bilge rat TAs will notice if they
lose too much fuel.
{{% /notice %}}

4. Next, liberate some of that glorious cargo.

- Define another anonymous function with an array as a parameter, and set it equal to another innocent variable.
- You need to swipe two items from the cargo hold.  Choose well. Stealing water ain't gonna get us rich.  Put the swag into a new array and return it from the function.
- The cargo hold has better security than the fuel tanks.  It counts how many things are in storage. You need to replace what you steal with something worthless.  The count MUST stay the same, or you'll get caught and thrown into the LaunchCode brig.
- Don't get hasty, matey! Remember to test your function.

5. Finally, you need to print a receipt for the accountant. Don't laugh! That genius knows MATH and saves us more gold than you can imagine.

- Define a function called `irs` that can take `fuelLevel` and `cargoHold` as arguments.

   {{% expand "Check Your Solution" %}}
   ```javascript
   let irs = function(levelOfFuel, itemsInCargo) {

   }
   ```
   {{% /expand %}}

- Call your anonymous fuel and cargo functions from within `irs`.
- Use a template literal to return, `"Raided _____ kg of fuel from the tanks, and stole ____ and ____ from the cargo hold."`

   {{% expand "Check Your Solution" %}}
   ```javascript
   let irs = function(levelOfFuel, itemsInCargo {
      let arr = deckMops(itemsInCargo);
      return `Raided ${nonSuspiciousFunction(fuelLevel)} kg of fuel from the tanks, and stole ${arr[0]} and ${arr[1]} from the cargo hold.`
   }
   ```
   {{% /expand %}}
