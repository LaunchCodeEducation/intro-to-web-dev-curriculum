---
title: "Test-Driven Development"
date: 2023-09-06T13:40:41-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Now that we know more about unit tests, we are going to learn a new way of using them.
So far we have written tests to verify functionality of *existing* code. Next we are going
to use tests to verify functionality of code that does NOT already exist. This may sound
odd, but this process has many benefits as we will learn.

As the name sounds, **Test-driven development (TDD)** is a software development
process where the unit tests are written first. However, that doesn't tell the
entire story. Writing the tests first and intentionally thinking more about the
code design leads to better code. The name comes from the idea of the tests
*driving* the development process.

Before we can start using TDD, we need a list of discrete features that can be turned into
unit tests. This will help keep our tests focused on specific functionality which should
lead to code that is easy to read. Along the way we will build confidence as we add features.

{{% notice blue "Note" "rocket" %}}

   TDD is a process that some organizations choose to use. Using the TDD
   process is not required when using unit tests.

{{% /notice %}}

## The Test/Code Cycle

With TDD you start with the unit test first. Each test must *clearly describe*
the behavior it is testing.

{{% notice blue "Example" "rocket" %}}

   Example test case for a data parsing project:

   * Take in a string of numbers delimited by a character and return an array.

{{% /notice %}}

Because the test is for a feature that does NOT exist *yet*, we need to think
about how the feature will be implemented. This is the time to ask questions
like: *Should we add a new parameter? What about an entirely new function?
What will the function return?*

{{% notice blue "Example" "rocket" %}}

   How could we implement our test case? Remember we aren't writing the code
   yet, only thinking about the design.

   * The test case will evaluate the function named `parseData`
   * The `parseData` function will:

     * contain a `data` parameter that gets assigned a string of data
     * contain a `delimiter` parameter that will be used to split the string
       into an array
     * return an array

   * `parseData` will be defined in a module

{{% /notice %}}

Next, write the unit test as if the parameter or function you imagined already
exists. This may seem a bit odd, but considering how the new code will be used
helps find bugs and flaws earlier. We also have to use test utilities such as
`expect().toBe()` to clearly demonstrate that the proposed new code
functions properly.

{{% notice blue "Example" "rocket" %}}

   Next, type out the ideas into an actual test. In this example, the test
   references a module and a function that have not been created yet. The code
   follows the plan we came up with earlier. Very importantly, there is an
   `expect().toBe(true)` that verifies an array is returned.

   ```js {linenos=true}
      const parse = require('../parse-numbers');

      describe("parse numbers", function(){

         test("returns array when passed comma separated list of numbers", () => {
            let items = parse("5,8,0,17,6,4,9,3", ",");
            expect(Array.isArray(items)).toBe(true);
         });

      });
```

{{% /notice %}}

Now run the test! The test should fail (or not compile at all) because you have
referenced code that does not exist yet.

Finally, write code to pass the new test. In the earlier chapters, this is
where you started, but with TDD writing new code is the *last* step.

{{% notice blue "Example" "rocket" %}}

   To make the new test pass, a file must be created that exports a
   `parseData` function with logic that satisfies the expected result.

   ```js {linenos=true}
      function parseData(text, delimiter) {
         return text.split(delimiter);
      }

      module.exports = parseData;
   ```

{{% /notice %}}

Coding this way builds confidence in your work. No matter how large your code
base may get, you know that each part has a test to validate its functionality.

{{% notice blue "Example" "rocket" %}}

   Now that we have one passing test for our data parser project, we could
   confidently move on to writing tests and code for the remaining features.

{{% /notice %}}

## Red, Green, Refactor

While adding new features and making our code work is the main goal, we also
want to write readable, efficient code that makes us proud. The **red, green,
refactor** mantra describes the process of writing tests, seeing them pass, and
then making the code better. As the name suggests, the cycle consists of three
steps. Red refers to test results that fail, while green represents tests that
pass. The colors refer to test results which are often styled with red for
failing tests and green for passing tests.

1. Red -> Write a failing test.
1. Green -> Make it pass by implementing the code.
1. Refactor -> Make the code better.

![Graphic showing the cycle of phases from red the writing test, green making the test pass, and blue of refactoring code to be better which points back to red](pictures/red-green-refactor.png)

**Refactoring code** means to keep the same overall feature, but change how
that feature is implemented. Since we have a test to verify our code, we can
change the code with confidence, knowing that any error will be immediately
identified by the test. Here are a few examples of refactoring:

1. Using different data structures,
1. Reducing the number of times needed to loop through an array,
1. Moving duplicate logic into a function so it can be reused.

The refactor is also done in a TDD process:

1. Decide how to improve the implementation of the feature,
1. Change the unit test to use this new idea,
1. Run the code to see the test fail,
1. Refactor the code to implement the new idea,
1. Finally, see the test pass with the refactored design.