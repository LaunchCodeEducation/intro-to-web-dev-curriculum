# Exercises: Arrays

OK, rookie. It\'s time to train you on how to modify the shuttle\'s
cargo manifest. The following actions will teach you how to add, remove,
modify and rearrange our records for the items stored in our hold.

1.  Create an array called `practiceFile` with the following entry:
    273.15. Use the `push` method to add the following elements to the
    array. Add items a & b one at a time, then use a single `push` to
    add the items in part c. Print the array after each step to confirm
    the changes.

    1.  42
    2.  \"hello\"
    3.  `false`, -4.6, \"87\"

    [Code it at repl.it](https://repl.it/@launchcode/ArrayExercises01)

    *Congratulations, rookie. You can now add items to an array.*

    `Check your solution <arrays-exercise-solutions1>`{.interpreted-text
    role="ref"}.

2.  `push`, `pop`, `shift` and `unshift` are used to add/remove elements
    from the beginning/end of an array. **Bracket notation** can be used
    to modify any element within an array. Starting with the `cargoHold`
    array
    `['oxygen tanks', 'space suits', 'parrot', 'instruction manual', 'meal packs', 'slinky', 'security blanket']`,
    write statements to do the following:

    1.  Use bracket notation to replace `'slinky'` in the array with
        `'space tether'`. Print the array to confirm the change.
    2.  Remove the last item from the array with `pop`. Print the
        element removed and the updated array.
    3.  Remove the first item from the array with `shift`. Print the
        element removed and the updated array.
    4.  Unlike `pop` and `shift`, `push` and `unshift` require arguments
        inside the `()`. Add the items 1138 and \'20 meters\' to the
        array -the number at the start and the string at the end. Print
        the updated array to confirm the changes.
    5.  Use a template literal to print the final array and its length.

    [Code it at repl.it](https://repl.it/@launchcode/ArrayExercises02)

    *Status check, rookie. Which array methods ADD items, and where are
    the new entries placed? Which methods REMOVE items, and where do the
    entries come from? Which methods require entries inside the
    \`\`()\`\`?*

    `Check your solution <arrays-exercise-solutions2>`{.interpreted-text
    role="ref"}.

3.  The `splice` method can be used to either add or remove items from
    an array. It can also accomplish both tasks at the same time. Review
    the `splice appendix <splice-examples>`{.interpreted-text
    role="ref"} if you need a syntax reminder. Use `splice` to make the
    following changes to the final `cargoHold` array from exercise 2. Be
    sure to print the array after each step to confirm your updates.

    1.  Insert the string `'keys'` at index 3 without replacing any
        other entries.
    2.  Remove \'instruction manual\' from the array. (Hint: `indexOf`
        is helpful to avoid manually counting an index).
    3.  Replace the elements at indexes 2 - 4 with the items `'cat'`,
        `'fob'`, and `'string cheese'`.

    [Code it at repl.it](https://repl.it/@launchcode/ArrayExercises03)

    `Check your solution <arrays-exercise-solutions3>`{.interpreted-text
    role="ref"}.

    *Well done, cadet. Now let\'s look at some finer details about array
    methods. We\'ve got to keep our paperwork straight, so you need to
    know when your actions change the original records.*

4.  Some methods\-\--like `splice` and `push`\-\--alter the original
    array, while others do not. Use the arrays

    ``` js
    holdCabinet1 ['duct tape', 'gum', 3.14, false, 6.022e23]
    ```

    and

    ``` js
    holdCabinet2 ['orange drink', 'nerf toys', 'camera', 42, 'parsnip']
    ```

    to explore the following methods: `concat`, `slice`, `reverse`,
    `sort`. Refer back to the chapter if you need to review the proper
    syntax for any of these methods.

    1.  Print the result of using `concat` on the two arrays. Does
        `concat` alter the original arrays? Verify this by printing
        `holdCabinet1` after using the method.
    2.  Print a `slice` of two elements from each array. Does `slice`
        alter the original arrays?
    3.  `reverse` the first array, and `sort` the second. What is the
        difference between these two methods? Do the methods alter the
        original arrays?

    [Code it at repl.it](https://repl.it/@launchcode/ArrayExercises04)

    *Good progress, cadet. Here are two more methods for you to
    examine.*

    `Check your solution <arrays-exercise-solutions3>`{.interpreted-text
    role="ref"}.

5.  The `split` method converts a string into an array, while the `join`
    method does the opposite.

    1.  Try it! Given the string
        `str = 'In space, no one can hear you code.'`, see what happens
        when you print `str.split()` vs. `str.split('e')` vs.
        `str.split(' ')` vs. `str.split('')`. What is the purpose of the
        parameter inside the `()`?
    2.  Given the array `arr = ['B', 'n', 'n', 5]`, see what happens
        when you print `arr.join()` vs. `arr.join('a')` vs.
        `arr.join(' ')` vs. `arr.join('')`. What is the purpose of the
        parameter inside the `()`?
    3.  Do `split` or `join` change the original string/array?
    4.  The benefit, cadet, is that we can take a string with
        **delimiters** (like commas) and convert it into a modifiable
        array. *Try it!* Alphabetize these hold contents: \"water,space
        suits,food,plasma sword,batteries\", and then combine them into
        a new string.

    [Code it at repl.it](https://repl.it/@launchcode/ArrayExercises05)

    *Nicely done, astronaut. Now it\'s time to bring you fully up to
    speed.*

    `Check your solution <arrays-exercise-solutions4>`{.interpreted-text
    role="ref"}.

6.  Arrays can hold different data types, even other arrays! A
    **multi-dimensional array** is one with entries that are themselves
    arrays.

    1.  Define and initialize the following arrays, which hold the name,
        chemical symbol and mass for different elements:
        i.  `element1 = ['hydrogen', 'H', 1.008]`
        ii. `element2 = ['helium', 'He', 4.003]`
        iii. `element26 = ['iron', 'Fe', 55.85]`
    2.  Define the array `table`, and use `push(arrayName)` to add each
        of the element arrays to it. Print `table` to see its structure.
    3.  Use bracket notation to examine the difference between printing
        `table[1]` and `table[1][1]`. Don\'t just nod your head! I want
        to HEAR you describe this difference. Go ahead, talk to your
        screen.
    4.  Using bracket notation and the `table` array, print the mass of
        element1, the name for element 2 and the symbol for element26.
    5.  `table` is an example of a *2-dimensional array*. The first
        \"level\" contains the element arrays, and the second level
        holds the name/symbol/mass values. **Experiment!** Create a
        3-dimensional array and print out one entry from each level in
        the array.

    [Code it at repl.it](https://repl.it/@launchcode/ArrayExercises06)

    `Check your solution <arrays-exercise-solutions5>`{.interpreted-text
    role="ref"}.

*Excellent work, records keeper. Welcome aboard.*
