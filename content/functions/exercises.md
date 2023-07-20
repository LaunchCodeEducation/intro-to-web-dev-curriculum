# Exercises: Functions

To solve problems with code, you need to be able to break large problems
into small ones. Usually, these smaller problems will take the form of
functions that are used to solve the larger problem. Therefore, to solve
problems with code, you need to be skilled at writing functions. And to
master functions, you need to write a *lot* of them.

These exercises ask you to write many relatively small functions, which
combine to form larger, more complicated ones.

At the end, you will be able to create strings of shapes, like this
nifty diamond:

    #
    ###
    #####
    #######
    #########
    #########
    #######
    #####
    ###
    #

There is no starter code for these exercises, so create a new Node.js
project at [repl.it](https://repl.it/login) to get started.

## Rectangles

A.  Write a function `makeLine(size)` that returns a line with exactly
    `size` hashes.

    ``` js
    console.log(makeLine(5));
    ```

    **Console Output**

        #####

    `Check your solution <functions-exercise-solutionsA>`{.interpreted-text
    role="ref"}.

B.  Write a function called `makeSquare(size)` that returns a `size` by
    `size` string of hashes. The function should NOT print each row of
    the square. Instead, it must return a single string that contains
    the entire shape.

    ::: admonition
    Tip

    1.  Call your `makeLine` function to create each row of the square.
    2.  The newline character, `\n`, will be helpful to you.
    3.  Do NOT include a newline character at the end of your string.
    :::

    ``` js
    console.log(makeSquare(5));
    ```

    **Console Output**

        #####
        #####
        #####
        #####
        #####

    ::: admonition
    Warning

    For each of the shape exercises, do not include a newline character
    at the very end of your string. While the final `\n` might not be
    noticeable for the simpler shapes, including it will make life
    harder for you toward the end of the exercises.
    :::

C.  Write a function `makeRectangle(width, height)` that returns a
    rectangle with the given width and height. Use your `makeLine`
    function to do this.

    ``` js
    console.log(makeRectangle(5, 3));
    ```

    **Console Output**

        #####
        #####
        #####

    `Check your solution <functions-exercise-solutionsC>`{.interpreted-text
    role="ref"}.

D.  Now, go back and rewrite `makeSquare` to use `makeRectangle`.

## Triangles

E.  Write a function `makeDownwardStairs(height)` that prints the
    staircase pattern shown below, with the given height. Use your
    `makeLine` function to do this.

    ``` js
    console.log(makeDownwardStairs(5));
    ```

    **Console Output**

        #
        ##
        ###
        ####
        #####

    `Check your solution <functions-exercise-solutionsE>`{.interpreted-text
    role="ref"}.

F.  Write a function `makeSpaceLine(numSpaces, numChars)` that returns a
    line with exactly the specified number of spaces, followed by the
    specified number of hashes, followed again by `numSpaces` more
    spaces.

    ``` js
    console.log(makeSpaceLine(3, 5));
    ```

    **Console Output**

        ___#####___

    ::: note
    ::: title
    Note
    :::

    We have inserted underscores to represent spaces, so they are
    visible in the output. Don\'t do this in your code.
    :::

G.  Write a function `makeIsoscelesTriangle(height)` that returns a
    triangle of the given height.

    ``` js
    console.log(makeIsoscelesTriangle(5));
    ```

    **Console Output**

        #
        ###
        #####
        #######
        #########

    ::: tip
    ::: title
    Tip
    :::

    Consider the top line of the triangle to be level 0, the next to be
    line 1, and so on. Then line `i` is a space-line with
    `height - i - 1` spaces and `2 * i + 1` hashes.
    :::

    `Check your solution <functions-exercise-solutionsG>`{.interpreted-text
    role="ref"}.

## Diamonds

H.  Write a function `makeDiamond(height)` that returns a diamond where
    the triangle formed by the *top* portion has the given height.

    ``` js
    console.log(makeDiamond(5));
    ```

    **Console Output**

        #
        ###
        #####
        #######
        #########
        #########
        #######
        #####
        ###
        #

    ::: tip
    ::: title
    Tip
    :::

    Consider what happens if you create a triangle and reverse it using
    `our reverse function <reverse_func>`{.interpreted-text role="ref"}.
    :::

## Bonus Mission

Refactor your functions so that they take a single character as a
parameter, and draw the shapes with that character instead of always
using `'#'`. Make the new parameter optional, with default value `'#'`.
