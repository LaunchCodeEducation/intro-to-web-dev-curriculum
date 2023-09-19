---
title: "Exercises: Classes"
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

Welcome to the space station!
It is your first day onboard and as the newest and most junior member of the
crew, you have been asked to organize the library of manuals and fun novels for
the crew to read. 

Headquarters have asked that you store the following information about each
book.

1. The title
1. The author
1. The copyright date
1. The ISBN
1. The number of pages
1. The number of times the book has been checked out.
1. Whether the book has been discarded.

Headquarters also needs you to track certain actions that you must perform when
books get out of date. First, for a manual, the book must be thrown out if it
is over 5 years old. Second, for a novel, the book should be thrown out if it
has been checked out over 100 times.

Open `ClassExercises.js` in `javascript-projects/classes/exercises` to get started.

1. Construct three classes that hold the information needed by headquarters as
properties. One class should be a `Book` class and two
child classes of the `Book` class called `Manual` and `Novel`. 
Each class will contain two methods. One will be a constructor. The other one will either be in charge of disposal of the book or updating the property related to the number of times a book has been checked out.
`Hint:` This means you need to read through the requirements for the problem and decide what should belong to `Book` and what should belong to the `Novel` and
`Manual` classes. 

{{% expand "Check your solution" %}}

```js {linenos=table}
class Book {
   constructor(title, author, copyright, isbn, pages, timesCheckedOut, discarded){
      this.title = title;
      this.author = author;
      this.copyright = copyright;
      this.isbn = isbn;
      this.pages = pages;
      this.timesCheckedOut = timesCheckedOut;
      this.discarded = discarded;
   }

   checkout(uses=1) {
      this.timesCheckedOut += uses;
   }
}

class Manual extends Book {
   constructor(title, author, copyright, isbn, pages, timesCheckedOut, discarded){
      super(title, author, copyright, isbn, pages, timesCheckedOut, discarded);
   }

   dispose(currentYear){
      if (currentYear-this.copyright > 5) {
         this.discarded = 'Yes';
      }
   }
}

class Novel extends Book {
   constructor(title, author, copyright, isbn, pages, timesCheckedOut, discarded){
      super(title, author, copyright, isbn, pages, timesCheckedOut, discarded);
   }

   dispose(){
      if (this.timesCheckedOut > 100) {
         this.discarded = 'Yes';
      }
   }
}
```

{{% /expand %}}

2. Declare an object of the `Novel` class for the following tome from the
library:

| Variable | Value |
|----------|-------|
| Title | Pride and Prejudice |
| Author | Jane Austen |
| Copyright date | 1813 |
| ISBN | 1111111111111 |
| Number of pages | 432 |
| Number of times the book has been checked out | 32 |
| Whether the book has been discarded | No |

3. Declare an object of the `Manual` class for the following tome from the
library:

| Variable | Value |
|----------|-------|
| Title | Top Secret Shuttle Building Manual |
| Author | Redacted |
| Copyright date | 2013 |
| ISBN | 0000000000000 |
| Number of pages | 1147 |
| Number of times the book has been checked out | 1 |
| Whether the book has been discarded | No |

{{% expand "Check your solution" %}}

```js
let makingTheShip = new Manual('Top Secret Shuttle Building Manual', 'Redacted', 2013, '0000000000000', 1147, 1, 'No');
```

{{% /expand %}}

4. One of the above books needs to be discarded. Call the appropriate method
for that book to update the property. That way the crew can throw it into empty
space to become debris.

5. The other book has been checked out 5 times since you first created the
object. Call the appropriate method to update the number of times the book has
been checked out.

{{% expand "Check your solution" %}}

```js
goodRead.checkout(5);
goodRead.dispose();
```

{{% /expand %}}