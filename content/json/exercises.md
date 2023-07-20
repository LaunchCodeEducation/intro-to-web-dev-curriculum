# JSON {#exercises-JSON}

1.  Which of the following three code snippets is correct JSON syntax?
    Why are the other two options incorrect?

    a.  .. sourcecode:: js

        > {
        >
        > :   type: \"dog\", name: \"Bernie\", age: 3
        >
        > }

    b.  ``` js
        {
           "type": "dog",
           "name": "Bernie",
           "age": 3
        }
        ```

    c.  ``` js
        > {
        >    "type": 'dog',
        >    "name": 'Bernie',
        >    "age": 3
        > }
        > ```

    `Check your solution <JSON-exercise-solutions1>`{.interpreted-text
    role="ref"}.

2.  Which of the following three code snippets is correct JSON? Why are
    the other two options incorrect?

    a\.

    > ``` js
    > {
    >    "animals": [
    >       {
    >             "type": "dog",
    >             "name": "Bernie",
    >             "age": 3
    >       },
    >       {
    >             "type": "cat",
    >             "name": "Draco",
    >             "age": 2
    >       }
    >    ]
    > }
    > ```

    b\.

    > ``` js
    > {
    >    [
    >       {
    >             "type": "dog",
    >             "name": "Bernie",
    >             "age": 3
    >       },
    >       {
    >             "type": "cat",
    >             "name": "Draco",
    >             "age": 2
    >       } 
    >    ]
    > }
    > ```

    c\.

    > ``` js
    > [
    >    {
    >          "type": "dog",
    >          "name": "Bernie",
    >          "age": 3
    >    },
    >    {
    >          "type": "cat",
    >          "name": "Draco",
    >          "age": 2
    >    } 
    > ]
    > ```
