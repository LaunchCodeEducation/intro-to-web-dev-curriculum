---
title: "Hello, Jest!"
date: 2023-09-06T13:40:41-05:00
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

In order to unit test our code, we need to use a module. Such a module is called a **unit-testing framework**, and there are [many to choose from](https://en.wikipedia.org/wiki/List_of_unit_testing_frameworks#JavaScript).

We will use [Jest](https://jestjs.io/), a popular JavaScript testing framework. We are using Jest because of it's popularity in industry, excellent developer support, and it is used for testing React applications, which we will learn more about in later lessons.

## Using Jest


Jest is an npm module that can be installed and used in a manner similar to
`readline-sync`. Jest will require that we first install it. We then will have to configure everything to make sure that Jest can run the tests in our project.

A project using Jest has several components:

1. A folder containing our tests. This folder is commonly called `tests`.
1. Test files within this folder. For example, if we wanted to test a function called `hello`, we might have a test file called `hello.test.js`.
1. `package.json` with Jest listed under `dependencies` or `devDependencies`.
1. Occasionally, you will find an extra configuration file called `jest.config.js`. This is used in cases where we want to use a different configuration from Jest's default options.

{{% notice orange "Warning" "rocket" %}}

   Jest can be set up and used in many different ways. If you are looking for an answer on the Internet (like on Stack Overflow or in the documentation) you will see widely varying usages of Jest that may not seem to apply to your situation. For example, maybe another developer on Stack Overflow stores their tests in a folder called `spec` or `_tests_`. 

{{% /notice %}}

## Hello, Jest!

Let's build a "Hello, World!" Jest project, to get familiar with the basic components. Open the `hello-jest` directory in the `chapter-examples` folder in `javascript-projects/unit-testing`.

We will walk you through the steps needed to get a simple Jest project up and running. Code along with us throughout this section. Run `npm install` in your terminal to make sure that your project is ready to run when you want to see how the code works.

### `hello.js`

Open `hello.js` and review the code inside:

```js {linenos=table}
function hello(name) {
   if (name === undefined)
      name = "World";

   return "Hello, " + name + "!";
}
```

The `hello` function takes a single argument representing a person's name and returns a string greeting that person. If the function is called without an argument, the function returns `"Hello, World!"`.

To use this function outside `hello.js` we must export it at the bottom of the file.

```js
module.exports = hello;
```

### `tests/hello.test.js`

Now that we have a function to test, let's write some test code. Add a folder named `tests` to the project. Within the folder, create the file `hello.test.js`. It is conventional to put tests for `fileName.js` in `tests/fileName.test.js`. This makes it easy to find the tests associated with a given file.

At the top of the `hello.test.js` file, review the import of your function from `hello.js`:

```js {linenos=table}
   const hello = require('../hello.js');
```

Below that, there is a call to the function `describe`, passing in the name of the function we want to test along with an empty anonymous function. `describe` is a Jest function that is used to define a **test suite**, a group of related tests. These related tests are placed *within* the anonymous function to be run together as a suite.

```js
describe("hello", function(){

});
```

### Specifications and Expectations

There are two cases we want to test:

1. The function is called with a string argument. In this case, a customized greeting should be returned.
1. The function is called with no argument. In this case, the general greeting should be returned.

Within `describe`'s function argument, review the test for case 1:

```js {linenos=true}
test("should return custom message when name is specified", function() {
   expect(hello("Jest")).toBe("Hello, Jest!");
});
```

The `test` function is part of the Jest framework as well. Calling `test` creates a **specification**, or **spec**, which is a description of expected behavior. The first argument to `test` is a string describing the desired behavior. This string serves to document the test and is also used in reporting test results. These strings will usually begin with "should", followed by a desired action.

The second argument to `test` is called a  function. This function contains the test code itself, which takes the form of an **expectation**. An expectation is a declaration of desired behavior *in code*. Let's examine the contents of the arrow function:

```js
expect(hello("Jest")).toBe("Hello, Jest!");
```

Calling `expect(x).toBe(y)` declares that we expect `x` to equal `y`.
As you get started with unit testing, nearly *all* of your tests will take this form.
The argument to `expect()` is a call to the function `hello()`. The argument to `toBe()` is the expected output from that function call. 
`toBe()` is a specialized method called a **matcher**. Matchers in Jest compare the value passed to the value passed to `expect()`.
These comparisons are not just limited to checking if the two values are equal. Jest has a wide variety of matchers built-in and developers can also build custom matchers.
For a full list of the provided matchers, check out the [Jest documentation](https://jestjs.io/docs/using-matchers).

If the two arguments are indeed equal, the test will pass. Otherwise, the test will fail. In this case, we are declaring that we *expect* `hello("Jest")` to return the value `"Hello, Jest!"`.

Let's review the final spec for testing our other case.

```js
   test("should return a general greeting when name is not specified", function(){
        expect(hello()).toBe("Hello, World!");
    });
```

This spec declares that calling ``hello()`` should return ``"Hello, World!"``.

### Test Reporting

This is a fully-functioning test file. Run `npm test` in your terminal to run your tests. If all goes well, the output will look like this:

```console {linenos=table}
   > unit-testing@1.0.0 test
   > jest

   PASS  tests/hello.test.js
   hello world test
    ✓ should return a custom message when name is specified (2 ms)
    ✓ should return a general greeting when name is not specified

   Test Suites: 1 passed, 1 total
   Tests:       2 passed, 2 total
   Snapshots:   0 total
   Time:        0.69 s, estimated 1 s
   Ran all test suites.
```

The most important line in the output is this one:

```console
   2 passed, 2 total
```

It tells us that Jest found 2 test specifications, and that 0 of the specs failed. If our test had failed, then the line would have read:

```console
   0 passed, 2 total
```

In other words, *our tests passed!* 

Let's see what a test failure looks like. Go back to `hello.js` and remove the `"!"` from the return statement:

```js
   return "Hello, " + name;
```

Run the tests again. This time, the output looks quite different as we intentionally made tests fail. The failing tests appear below the list of tests run for this test suite. This
describes exactly what went wrong. For the first test, the expected value was `'Hello, Jest!'` but the received value `'Hello, Jest'`.
Notice that the failure description is the result of joining the two string arguments from `describe` and `test`.
This is why we intentionally defined those strings the way we did.

Put `hello.js` back as it was and run the tests again to make sure it works.

### Check Your Understanding

{{% notice green "Question" "rocket" %}}

   Examine the function below, which checks if two strings match:

   ```js {linenos=table}
   function doStringsMatch(string1, string2){
      if (string1 === string2) {
         return 'Strings match!';
      } else {
         return 'No match!';
      }
   }
   ```

   Which of the following tests checks if the function properly handles
   case-*sensitive* answers.

   1. `expect(doStringsMatch('Flower', 'Flower')).toBe('Strings match!');`
   1. `expect(doStringsMatch('Flower', 'flower')).toBe('No match!');`
   1. `expect(doStringsMatch('Flower', 'plant')).toBe('No match!');`
   1. `expect(doStringsMatch('Flower', '')).toBe('No match!');`

{{% /notice %}}

<!-- 1 -->