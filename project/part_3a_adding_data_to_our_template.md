### Part 3A: Adding Data to Your Template

Your template is working and looks pretty, but it’s hardcoded, or, in other words, the data is fixed and can only be edited manually. Add a couple questions and answers to your component, and make the template render your quiz questions dynamically. In Part 3, you’ll do some set-up work for data to use in your template. Part 4 will be to integrate the data with your component’s template (HTML).

Later, you’ll be using an [API](http://bit.ly/CnCgloss) [Application Programming Interface], to allow your application to interface with a set of  questions and answers for your quiz. In order to make that transition go smoothly, you'll set-up your data in the same format that will come from the API.

1.  Copy the following code:

    ```
    this.questions = [
      {
        "text": "Florence Nightingale became known as \"the Lady With the Lamp\" during which war?",
        "answers": [
          {
            "correct": false,
            "text": "American Civil War"
          },
          {
            "correct": false,
            "text": "World War I"
          },
          {
            "correct": true,
            "text": "Crimean War"
          },
          {
            "correct": false,
            "text": "World War II"
          }
        ]
      },
      {
        "text": "In a quarter-mile race, which animal can be expected to win?",
        "answers": [
          {
            "correct": false,
            "text": "Lion"
          },
          {
            "correct": true,
            "text": "Pronghorn Antelope"
          },
          {
            "correct": false,
            "text": "Quarter Horse"
          },
          {
            "correct": false,
            "text": "Giraffe"
          }
        ]
      }
    ];
    ```

2. In Atom, open your *src/app/quiz/quiz.component.ts* file by double clicking on it in the left side Project Pane. In the `ngOnInit()` [method](http://bit.ly/CnCgloss), between the opening and closing curly braces, (`{}`), paste that code in.

Check your code against the answer key here: [[http://bit.ly/spa-3_1](http://bit.ly/spa-3_1)].


2.  Since we’re using TypeScript, we need to set types for the data that we just copied and pasted. This is one file *Angular CLI* won’t generate for us. <br> Create a new file in *src/app/quiz* &amp; name it **quiz.model.ts**.
3.  In *quiz.model.ts*, add the code found here [[http://bit.ly/spa-model](http://bit.ly/spa-model)]. Feel free to manually type or copy/paste.

  ![](../images/18.png)

1.  Now we’re going to import these into *quiz.component.ts*.

  1.  Open *src/app/quiz/quiz.component.ts* &amp; below the <span class="ref">import</span> at the top, add: <span class="new">import {} from &#039;./quiz.model&#039;;</span>
  2.  Place your cursor in the middle of <span class="ref">{}</span>. And type  <span class="new">A</span>. Sublime should give you an autocomplete suggestion of <span class="ref">Answer</span>. [Hit tab or enter/return key for it to autocomplete <span class="new">Answer</span> for you.]
  3.  Add a comma after <span class="ref">Answer</span> &amp; repeat process by typing <span class="new">Q</span> [for Question].Printed worksheets see: [http://bit.ly/spa-ts](http://bit.ly/spa-ts)![](/images/image05.gif)

1.  In the quiz.component.ts file, within the <span class="ref">OnInit</span> method, add: <span class="new">questions: Question[];</span><br>![](/images/image14.png)This uses the imported <span class="ref">Question</span> Model to set the type for <span class="ref">questions</span>, (the data we set earlier in <span class="ref">ngOnInit</span>).