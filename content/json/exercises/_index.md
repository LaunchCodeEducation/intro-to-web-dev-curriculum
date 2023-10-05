---
title: "Exercises: JSON"
date: 2023-10-03T14:33:43-05:00
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

1. Which of the following three code snippets is correct JSON syntax? Why are the other two options incorrect?

   a. 
      ```js {linenos=table}
      {
         type: "dog",
         name: "Bernie",
         age: 3
      }
      ```
   b. 
      ```js {linenos=table}
      {
         "type": "dog",
         "name": "Bernie",
         "age": 3
      }
      ```
   c.
      ```js {linenos=table}
      {
         "type": 'dog',
         "name": 'Bernie',
         "age": 3
      }
      ```

   {{% expand "Check your solution" %}}
   a. This not correct JSON syntax because keys in JSON need to be strings.
   b. This is the only correct option.
   c. This not correct JSON syntax because, unlike JavaScript, JSON only uses double quotation marks ("")
   {{% /expand %}}

2. Which of the following three code snippets is correct JSON? Why are the other two options incorrect?

   a.
      ```js {linenos=table}
      {
         "animals": [
            {
                  "type": "dog",
                  "name": "Bernie",
                  "age": 3
            },
            {
                  "type": "cat",
                  "name": "Draco",
                  "age": 2
            }
         ]
      }
      ```
   b.
      ```js {linenos=table}
      {
         [
            {
                  "type": "dog",
                  "name": "Bernie",
                  "age": 3
            },
            {
                  "type": "cat",
                  "name": "Draco",
                  "age": 2
            } 
         ]
      }
      ```
   c.
      ```js {linenos=table}
      [
         {
               "type": "dog",
               "name": "Bernie",
               "age": 3
         },
         {
               "type": "cat",
               "name": "Draco",
               "age": 2
         } 
      ]
      ```