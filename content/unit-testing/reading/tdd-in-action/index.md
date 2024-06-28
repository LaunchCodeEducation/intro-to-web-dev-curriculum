---
title: "TDD in Action"
date: 2023-09-06T13:40:41-05:00
draft: false
weight: 5
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Open `transmission-processor` in `javascript-projects/unit-testing/chapter-examples`
and follow along as we implement a project using TDD.

We need to write a Node module to process transmissions from the [Voyager1 probe](https://voyager.jpl.nasa.gov/mission/).

{{% notice blue "Example" "rocket" %}}

   Transmission

   ```js
      "1410::<932829840830053761>"
   ```

   Expected Result

   ```js
      {
         id: 1410,
         rawData: 932829840830053761
      }
   ```

{{% /notice %}}

## Requirements

The features for this project have already been broken down into
small testable units. Let's review them and then we will
take it slow, one step at a time.

1. Take in a transmission string and return an object.
1. Return `-1` if the transmission does NOT contain `"::"`.
1. Returned object should contain an `id` property.

   1. The value of `id` is the part of the transmission *before* the `"::"`.

1. The `id` property should be of type `Number`.
1. Returned object should contain a `rawData` property.

   1. The value of `rawData` is the part of the transmission *after* the `"::"`.

1. Return -1 for the value `rawData` if the `rawData` part of the transmission does NOT start with `<` and end with `>`.

## Requirement #1

*Requirement:* Take in a transmission string and return an object.

To get started on this we need to:

a. Create a blank test function.
b. Give the test a name that is a clear, testable statement.

Creating a blank test is easy, go to `processor.test.js` and add an empty test method.
Tests in Jest are declared with a `test` function.
Remember that tests go inside of the `describe` function, which along with the string
parameter describe the group of tests inside.

```js {linenos=true}
   describe("transmission processor", function() {

      test("", function() {

      });

   });
```

Give the test the name `"takes a string and returns an object"`.

```js {linenos=true}
   describe("transmission processor", function() {

      test("takes a string returns an object", function() {

      });

   });
```

Now that we identified a clear goal for the test, let's add logic and `expect` calls
in the test to verify the desired behavior. *But wait...* we haven't added anything
except an empty test at this point. There isn't any actual code to verify. That's okay,
this is part of the TDD process.

We are going to think about and visualize
how this feature should be implemented in code. Then we will write out in the test how
this new code will be used.

We need to think of something that will satisfy the statement
`test("takes a string and returns an object"`.
The `test` will be a function that is imported from a module. Below on line 1,
a `processor` function is imported from the `processor.js` module.

```js {linenos=table}
   const processor = require('../processor.js');

   describe("transmission processor", function() {

      test("takes a string and returns an object", () => {

      });

   });
```

We have an idea for a function named `processor` and we have imported it.
Keep in mind this function only exists as a concept and we are writing a test
to see if this concept makes sense.

Now for the real heart of the test. We are going to use `expect().toBe()` to
verify that if we pass a string to `processor`, an object is returned.
Carefully review lines 7 and 8 shown below.

```js {linenos=true}
   const processor = require('../processor.js');

   describe("transmission processor", function() {

      test("takes a string and returns an object", function() {
         let result = processor("9701::<489584872710>");
         expect(typeof result).toBe("object");
      });

   });
```

On line 6 the `processor` function is called, with the value being stored in a `result`
variable. On line 8 the result of the expression `typeof result` is compared to the value
`"object"`. Reminder that the `typeof` operator returns a string representation
of a type. If `typeof result` evaluates to the string `"object"`, then we know that `processor`
returned an object.

### Code Red

Let's run the test!

Type in the command `npm run test` to check your test.

You should see an error about `processor.js` not existing. This makes sense, because we have not
created the file yet. We are officially in the Red phase of Red, Green, Refactor!

```console
   Error: Cannot find module '../processor.js'
```

### Go Green!

Now that we have a failing test, we have only one choice. Make it pass.

1. Add a `processor.js` file to your project.
1. Inside of the module declare a `processor` function that takes a parameter and returns an object.

Contents of the new `processor.js` file.

```js {linenos=true}
   function processor(transmission) {
      return {};
   }

   module.exports = processor;
```

*Run the test again.*

### Refactor if Needed

This solution is very simple and does not need to be improved. The refactor step 
does not always lead to an actual changing of your code. The most important part is to
review your code to make sure that it's efficient and meets your team's standards.

## Requirement #2

*Requirement:* Return `-1` if the transmission does NOT contain `"::"`.

Next we have a negative test requirement that tells us what should happen if the data is invalid.
Before jumping into the code, let's review the steps we took to implement requirement #1.

Review of TDD process:

1. Create a blank test function.
1. Give the test a name that is a clear, testable statement.
1. Come up with test data that will trigger the described behavior.
1. Think about what is needed, then write code that fulfills the stated behavior.
1. Run the test and see the it fail.
1. Implement the new code or feature used in the test.
1. Run the test and see it pass.
1. Review to see if refactor needed.

For requirement #2, the solution for *steps 1 - 4* can be seen on lines *11 - 14* below.

```js {linenos=table}
   const processor = require('../processor.js');

   describe("transmission processor", function() {

      test("takes a string and returns an object", function() {
         let result = processor("9701::<489584872710>");
         expect(typeof result).toBe("object");
      });

      test("returns -1 if '::' not found", function() {
         let result = processor("9701<489584872710>");
         expect(result).toBe(-1);
      });

   });
```

Now for *step 5*, run the test and see it fail. Notice that `-1` was the expected value, but the actual value was
and empty object, `{}`.

Next is *step 6*, write code that will make the test pass. Go to `processor.js` and
update the `processor` function to check the `transmission` argument for the
presence of `'::'`.

```js {linenos=table}
   function processor(transmission) {
      if (transmission.indexOf("::") < 0) {
         // Data is invalid
         return -1;
      }
      return {};
   }

   module.exports = processor;
```

Lucky *step 7* is to run the tests again. They should both pass.

Finally *step 8* is to review the code to see if it needs to be refactored. As with the first requirement
our code is quite simple and can not be improved at this time.

## Requirement #3

*Requirement:* Returned object should contain an `id` property.
The `id` is the part of the transmission *before* the `"::"`.

The same steps will be followed, even though they are not explicitly listed.

See lines *16 - 19* to see the test added for this requirement. To test
this case `not.toBeUndefined()` was used, which is checking if the two values
are NOT equal. `not.toBeUndefined()` is used to make sure that `result.id`
is NOT equal to `undefined`. Remember that if you reference a property on an
object that does NOT exist, `undefined` is returned.

```js {linenos=table}
   const processor = require('../processor.js');

   describe("transmission processor", function() {

      test("takes a string returns an object", function() {
         let result = processor("9701::<489584872710>");
         expect(typeof result).toBe("object");
      });

      test("returns -1 if '::' not found", function() {
         let result = processor("9701<489584872710>");
         expect(result).toBe(-1);
      });

      test("returns id in object", function() {
        let result = processor("9701::<489584872710>");
        expect(result.id).not.toBeUndefined();
      });

   });
```

The fail message looks a little different than what we have seen. The phrase
"Expected 'actual' to be strictly unequal to" lets us know that the two values
were equal when we didn't expect them to be.

The object returned from `processor` doesn't have an `id` property. We need
to split the transmission on `'::'` and then add that value to the object
with the key `id`. See solution in `processor.js` below.

```js {linenos=true}
   function processor(transmission) {
      if (transmission.indexOf("::") < 0) {
         // Data is invalid
         return -1;
      }
      let parts = transmission.split("::");
      return {
         id: parts[0]
      };
   }

   module.exports = processor;
```

Run the tests again. That did it. The tests pass!

Line 6 splits `transmission` into the `parts` array, and line 8 assigns
the first entry in the array to the key `id`.

### Requirement #4

*Requirement:* The `id` property should be of type `Number`.

Again the same steps are followed, though not listed.

New test to be added to `tests/processor.test.js`:

```js {linenos=true}
   test("converts id to a number", function() {
      let result = processor("9701::<489584872710>");
      expect(result.id).toBe(9701);
   });
```

This test fails. Looks like we need to convert `id` to a number. Time to update the code in `processor.js`.

```js {linenos=table}
function processor(transmission) {
   if (transmission.indexOf("::") < 0) {
      // Data is invalid
      return -1;
   }
   let parts = transmission.split("::");
   return {
      id: Number(parts[0])
   };
}

module.exports = processor;
```

Now for the great feeling of a passing tests!

{{% notice blue "Note" "rocket" %}}

   You may be wondering what happens if that data is bad and the id can't be
   turned into a number. That is a negative test case related to this feature
   and is left for you to address in the final section.

{{% /notice %}}

## Requirement #5

*Requirement:* Returned object should contain a `rawData` property. The `rawData`
is the part of the transmission *after* the `"::"`.

New test to be added to `tests/processor.test.js`:

```js {linenos=table}
   test("returns rawData in object", () => {
      let result = processor("9701::<487297403495720912>");
      expect(result.rawData).not.toBeUndefined();
   });
```

Let's run the tests again to see where we are at.

We need to extract the `rawData` from the second half of the transmission
string after it's been split. Then return that in the object.

```js {linenos=table}
   function processor(transmission) {
      if (transmission.indexOf("::") < 0) {
         // Data is invalid
         return -1;
      }
      let parts = transmission.split("::");
      let rawData = parts[1];
      return {
         id: Number(parts[0]),
         rawData: rawData
      };
   }

   module.exports = processor;
```

It's that time again, our tests pass!

## Requirement #6

*Requirement:* Return `-1` for the value `rawData` if the `rawData` part of
the transmission does NOT start with `<` and end with `>`.

Let's think about what test data to use for this requirement. What ways could the
transmission data be invalid?

1. It could be missing `<` at the beginning
1. It could be missing `>` at the end
1. It could be missing both `<` and `>`
1. Has `<` but the symbol is in the wrong place
1. Has `>` but the symbol is in the wrong place

All these cases need to be covered by a test. Let's start with #1, which
is missing `<` at the beginning.

New test to be added to `tests/processor.test.js`:

```js {linenos=table}
   test("returns -1 for rawData if missing < at position 0", function() {
      let result = processor("9701::487297403495720912>");
      expect(result.rawData).toBe(-1);
   });
```

Run the tests and review the fail message.

Now add new code to `processor.js` to make the tests pass. Note that we don't
simply return `-1`, the requirement is to return the object and set the value
of `rawData` to `-1`.

```js {linenos=table}
   function processor(transmission) {
      if (transmission.indexOf("::") < 0) {
         // Data is invalid
         return -1;
      }
      let parts = transmission.split("::");
      let rawData = parts[1];
      if (rawData[0] !== "<") {
         rawData = -1;
      }
      return {
         id: Number(parts[0]),
         rawData: rawData
      };
   }

   module.exports = processor;
```

You know what's next, our tests pass!

{{% notice blue "Example" "rocket" %}}

   The test data we used was missing `<` at the beginning. Add tests
   to cover these cases. `-1` should be returned as the value for
   `rawData` for all of these.

   1. `"9701::8729740349572>0912"`
   1. `"9701::4872<97403495720912"`
   1. `"9701::487297403495720912"`
   1. `"9701::<487297403495<720912>"`

{{% /notice %}}

## Use TDD to Add These Features

Use the steps demonstrated above to implement all or some of the features
below. Take your time, you can do it!

1. Trim leading and trailing whitespace from `transmission`.
1. Return `-1` if the `id` part of the `transmission` cannot be converted
   to a number.
1. Return `-1` if more than one `"::"` is found in `transmission`.
1. Do not include the `< >` symbols in the value assigned to `rawData`.
1. Return `-1` for the value of `rawData` if anything besides numbers are
   present between the `< >` symbols.
