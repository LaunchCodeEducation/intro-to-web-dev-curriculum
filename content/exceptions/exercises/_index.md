---
title: "Exercises: Exceptions"
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

## Zero Division: Throw

Write a function called divide that takes two parameters: a `numerator` and a
`denominator`.

Your function should return the result of `numerator / denominator`.

However, if `denominator` is zero you should throw the error, `"Attempted to divide by zero."`

{{% notice blue Note "rocket" %}}
Hint: You can use an `if / throw` statement to complete this exercise.
{{% /notice %}}

Code your function within the `javascript-projects/exceptions/exercises/divide.js`

   {{% expand "Check Your Solution" %}}
   ```javascript
   function divide(numerator, denominator) {
      if (denominator === 0) {
         throw Error('You cannot divide by zero!');
      }
      return numerator/denominator;
   }
   ```
   {{% /expand %}}

## Test Student Labs

{{% notice blue Note "rocket" %}}
The following starter code can be found at `javascript-projects/exceptions/exercises/test-student-labs.js`
{{% /notice %}}

A teacher has created a `gradeLabs` function that verifies if student
programming labs work. This function loops over an array of JavaScript objects
that *should* contain a `student` property and `runLab` property.

The `runLab` property is expected to be a function containing the student's
code. The `runLab` function is called and the result is compared to the
expected result. If the result and expected result don't match, then the lab is
considered a failure.

```javascript
function gradeLabs(labs) {
  for (let i=0; i < labs.length; i++) {
      let lab = labs[i];
      let result = lab.runLab(3);
      console.log(`${lab.student} code worked: ${result === 27}`);
  }
}

let studentLabs = [
  {
      student: 'Carly',
      runLab: function (num) {
        return Math.pow(num, num);
      }
  },
  {
      student: 'Erica',
      runLab: function (num) {
        return num * num;
      }
  }
];

gradeLabs(studentLabs);
```

The `gradeLabs` function works for the majority of cases. However, what
happens if a student named their function incorrectly? Run `gradeLabs` and
pass it `studentLabs2` as defined below.

```javascript
let studentLabs2 = [
  {
      student: 'Blake',
      myCode: function (num) {
        return Math.pow(num, num);
      }
  },
  {
      student: 'Jessica',
      runLab: function (num) {
        return Math.pow(num, num);
      }
  },
  {
      student: 'Mya',
      runLab: function (num) {
        return num * num;
      }
  }
];

gradeLabs(studentLabs2);
```

Upon running the second example, the teacher gets `TypeError: lab.runLab is not a function`.

Add a `try/catch` block inside of `gradeLabs` to catch an exception if the
`runLab` property is not defined. If the exception is thrown, `result`
should be set to the text `"Error thrown"`.
