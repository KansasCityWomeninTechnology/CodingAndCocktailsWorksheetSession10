# Part 5: Tally Correct Answers & Show Results

Now you have questions and answers to create a quiz, but at the end of the quiz, the user won’t know how many they answered correctly. Add a counter that keeps track of the correct answers throughout a quiz and displays the results at the end!

1.  Copy the code below:

  ```
  {% raw %}<div class="results" *ngIf="quizIsOver">
   <div class="result-message">
     You answered {{correctAnswers}} out of {{questions.length}} questions correctly.
   </div>
   <div class="score">That's {{ correctAnswers / questions.length * 100 }}%</div>
   <div class="result-action">Grab a cocktail &amp; celebrate!</div>
  </div>{% endraw %}
  ```

2. In Atom, paste the code into your *src/app/quiz/quiz.component.html* file before the final closing `</div>` HTML tag.

  ![](/images/image16.png)

  {% hint style='info' %}
### What does this code do?
  - The `div` HTML element with the `class="results"` only shows **if** the `quizIsOver`
  - The `div` HTML element with the `class="result-message"` tells the user how many `correctAnswers` they had out of the total number of questions
  - The `div` HTML element with the `class="score"` calculates and displays the percentage of correct answers
  - The `div` HTML element with the `class="result-action"` displays a fun message
  - `quizIsOver` and `correctAnswers` are highlighted because you still need to define those methods in the _quiz.component.ts_ file.
  {% endhint %}

3.  In Atom, open the *src/app/quiz/quiz.component.ts* file.

4.  On the next line below the `questions: Question[];` code, add 3 new variables and their data types. Type: `correctAnswers: number;`

5. Press enter to write the next variable on the next line.

6. Type: `currentQuestionIndex: number;`

7. Repeat that process to add the final variable: `quizIsOver: boolean;`

  ![](/images/image35.png)

8. Next, in Atom, in the same _src/app/quiz/quiz.component.ts_ file, find the `ngOnInit` function. Before the `this.questions` code, set default values for these 3 new variables that you just created. Place your cursor after the opening curly brace of the `ngOnInit() {` line and press enter.

  1. Type: `this.correctAnswers = 0;` then press enter to move to the next line.

  2. Type: `this.currentQuestionIndex = 0;` then press enter to move to the next line.

  3. Type: `this.quizIsOver = false;`

      ![](/images/image39.png)

      {% hint style='info' %}
##### Why these defaults?
  - `correctAnswers` and `currentQuestionIndex` both start at 0 because the quiz hasn't started yet.
  - `quizIsOver` starts as false because the quiz can't be over if it hasn't started yet.
      {% endhint %}

9. Increment your `correctAnswers` variable, every time an answer is correct.

  1. Find the `onSelect` method towards the bottom of the file. Place your cursor at the end of the `if (answer.correct) {` line of code and press enter.  You're now in the body of the if statement. Type: `this.correctAnswers++;`

    ![Screen Shot 2016-10-08 at 11.51.11 AM.png](/images/image19.png)

    {% hint style='info' %}
That line of code will update the value of the `correctAnswers` variable by one each time that line of code is hit (when the `answer` is `correct`).

`++` is a common way of incrementing a number by one in many programming languages!
    {% endhint %}

10. Next, increment the `currentQuestionIndex` variable by one, every time an answer is selected (correct or not).

  1. The `if` statement has an `else` clause as well. Place your cursor after the closing `}` for the `else` clause and press return.  

  2. Type: `this.currentQuestionIndex++;`

      ![Screen Shot 2016-10-08 at 11.54.05 AM.png](/images/image07.png)

  3.  Press return to move to the next line and type:
      `if (this.currentQuestionIndex === this.questions.length) {`

      Notice Atom automatically adds the closing curly brace `}` for you.

  4. Press return and set the `quizIsOver` variable to the value `true` in the if statement body.  Type: `this.quizIsOver = true;`

      ![Screen Shot 2016-10-07 at 9.49.59 PM.png](/images/image10.png)

      {% hint style='info' %}
When the `currentQuestionIndex` value is the same as the number of questions in the quiz (`questions.length` value), `quizIsOver` is set to true.
    {% endhint %}

  5. Save your _src/app/quiz/quiz.component.ts_ file.

11.  Right now, you see all the quiz questions at once. Even when the results display, the questions and answers are still visible. Add an `*ngIf` attribute, so you only see 1 question at a time.

  1.  Open the _src/app/quiz/quiz.component.html_ file. In the `<div class="q-and-a">` HTML element, add the attribute: `*ngIf="currentQuestionIndex === i"`

      ![](/images/image41.gif)

12.  **BONUS**: Add a tracker to the top of the quiz that tells the user which question they’re viewing.

  1.  In the *src/app/quiz/quiz.component.html* file, before the `<div class="quiz">` HTML element but after the opening `<div class="quiz-wrapper">` HTML element, paste the following code:

      ```
      {% raw %}<div
        class="question-tracker"
        *ngIf="!quizIsOver">
        Question {{currentQuestionIndex + 1}} of {{questions.length}}
      </div>
      <div
        class="results-header"
        *ngIf="quizIsOver">
        Results
      </div>{% endraw %}
      ```

      ![](/images/image40.png)

    **Challenge**: Can you explain to your neighbor what this is doing?

  2. Save the _src/app/quiz/quiz.component.html_ file.

![](../images/24.png)
