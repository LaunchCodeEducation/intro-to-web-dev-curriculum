---
title: "Introduction to React Forms"
date: 2023-04-12T16:25:46-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Now that we can handle events with React, let's talk about forms. When a form is submitted, the page reloads and the data is sent off to where it needs to go. In React, while form submission requires resetting the state back to the initial state, we can also experiment with changing the state.

Let's return to manufacturing. Since the shoe factory is having so many issues today, you have been asked to submit a full report online about what is happening. You want to make sure that the text you are entering into the form is accurate and grammatically correct. To be honest, we all can have a hard time editing the text in those text fields. So you add a preview section to the application so the user can review what they have entered and easily edit their work before submitting.

1. Open up the application we were working on in the last section. 
1. Create a new file in the `components` directory called `Report.js`.
1. Set up the initial form with one text area input box.

   ```jsx {linenos=table}
      import { useState } from 'react';

      export default function ReportForm() {
         return(
            <div>
               <form>
                  <label>Add your report here: <input type="textarea" />
                  </label>
                  <input type="submit" />
               </form>

               <p>Preview: </p>
            </div>);
      }
   ```

1. Now we can add one state variable called `notes` and start adding more functionality to our form!

   ```jsx {linenos=table}
      import { useState } from 'react';

      export default function ReportForm() {
         const [notes, setNotes] = useState("");

         return(
            <div>
               <form>
                  <label>Add your report here: <input type="textarea" value={notes} onChange={handleChange}/>
                  </label>
                  <input type="submit" />
               </form>

               <p>Preview: {notes}</p>
            </div>);
      }
   ```

1. We have added a new event handler called `handleChange()` to our form, but we haven't actually defined what `handleChange()` is yet.

   ```jsx {linenos=table}
      import { useState } from 'react';

      export default function ReportForm() {
         const [notes, setNotes] = useState("");

         const handleChange = (event) => {
            setNotes(event.target.value);
         }

         return(
            <div>
               <form>
                  <label>Add your report here: <input type="textarea" value={notes} onChange={handleChange}/>
                  </label>
                  <input type="submit" />
               </form>

               <p>Preview: {notes}</p>
            </div>);
      }
   ```

1. Now when a user types text into the form field, the state of the component is continually changed and the words the user types appear in the `<p>` element. 
1. Time to handle submission! We are going to set up a second event handler for this.

   ```jsx {linenos=table}
      import { useState } from 'react';

      export default function ReportForm() {
         const [notes, setNotes] = useState("");

         const handleChange = (event) => {
            setNotes(event.target.value);
         }

         const handleSubmit = (event) => {
            alert("Form submitted");
            event.preventDefault();
         }

         return(
            <div>
               <form onSubmit={handleSubmit}>
                  <label>Add your report here: <input type="textarea" value={notes} onChange={handleChange}/>
                  </label>
                  <input type="submit" />
               </form>

               <p>Preview: {notes}</p>
            </div>);
      }
   ```

1. We don't have anywhere to actually send our data, so all we need to do for now is create an alert popup and use `event.preventDefault()` to ensure the form does not actually submit.

When working with forms in React, you need to separate out what you would like to happen if the state changes versus when the state resets. A preview of a form field could be immensely helpful, but when form submission occurs, the state resets back to the initial state and the preview returns to an empty field.

{{% notice blue "Note" "rocket" %}}

   Check our completed manufacturing application on [GitHub](https://github.com/LaunchCodeEducation/react-pt3-example)!

{{% /notice %}}