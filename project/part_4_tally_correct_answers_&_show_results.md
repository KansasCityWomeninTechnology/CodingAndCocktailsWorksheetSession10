# Part 5: Tally Correct Answers & Show Results

Now you have questions and answers to create a quiz, but at the end of the quiz, the user won’t know how many they answered correctly. Add a counter that keeps track of the correct answers throughout a quiz and displays the results at the end!

1.  Copy the code below:

     ```
     <div class="results" *ngIf="quizIsOver">
       <div class="result-message">
         You answered {{correctAnswers}} out of {{questions.length}} questions correctly.
       </div>
       <div class="score">That's {{correctAnswers / questions.length * 100}}%</div>
       <div class="result-action">Grab a cocktail &amp; celebrate!</div>
     </div>
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

  1.  Below the `questions: Question[];` code, add 3 new variables and their data types. Type: `correctAnswers: number;` 
  
  2. Press enter to write the next variable on the next line. 
  
  3. Type: `currentQuestionIndex: number;`
  
  4. Repeat that process to add the final variable: `quizIsOver: boolean;`
  
      ![](/images/image35.png)
  
  5. Next, in Atom, in the same _src/app/quiz/quiz.component.ts_ file, find the `ngOnInit` function. Before the `this.questions` code, set default values for these 3 new variables that you just created. Place your cursor after the opening curly brace of the `ngOnInit() {` line and press enter. 
  
  6. Type: `this.correctAnswers = 0;` then press enter to move to the next line.
  
  7. Type: `this.currentQuestionIndex = 0;` then press enter to move to the next line.
  
  8. Type: `this.quizIsOver = false;`
  
      ![](/images/image39.png)
      
      {% hint style='info' %}
### Why these defaults?
      - `correctAnswers` and `currentQuestionIndex` both start at 0 because the quiz hasn't started yet.
      - `quizIsOver` starts as false because the quiz can't be over if it hasn't started yet.
      {% endhint %}

    1. We  need to increment our <span class="ref">correctAnswers</span> variable, every time an answer is correct.<br> In the <span class="ref">onSelect</span> method, within the <span class="ref">if (answer.correct) {...}</span> add: <span class="new">this.correctAnswers++;</span>![Screen Shot 2016-10-08 at 11.51.11 AM.png](/images/image19.png)<br>This will update the value of *correctAnswers* + 1, when the *answer* is *correct*.
  2.  We need to increment <span class="ref">currentQuestionIndex</span>, every time an answer is selected (correct or not).Below <span class="ref">onSelect’s else {...}</span> add: <span class="new">this.currentQuestionIndex++;</span>![Screen Shot 2016-10-08 at 11.54.05 AM.png](/images/image07.png)
  3.  Below <span class="ref">this.currentQuestionIndex++;</span> add: <span class="new">if (this.currentQuestionIndex === this.questions.length) {  this.quizIsOver = true;}</span><br>![Screen Shot 2016-10-07 at 9.49.59 PM.png](/images/image10.png)When the <span class="ref">currentQuestionIndex</span> value is the same as the <span class="ref">questions.length</span> value, <span class="ref">quizIsOver</span> is set to true.

1.  Right now, you see all the quiz questions at once. And even when the results display, the questions/answers are still visible. Let’s add an <span class="ref">*ngIf</span>, so we only see 1 question at a time.

1.  Open src/app/quiz/quiz.component.html. In <span class="ref">&lt;div class=&quot;q-and-a&quot;&gt;</span>, add attribute: <span class="new">*ngIf=&quot;currentQuestionIndex === i&quot;</span> <br>Printed worksheets see: [http://bit.ly/spa-if2](https://www.google.com/url?q=http://bit.ly/spa-if2&sa=D&ust=1479686156253000&usg=AFQjCNGB8a6X4JI9NMTbOP5237p1G--0VA)<br>![](/images/image41.gif)

1.  **BONUS**: Add a tracker to the top of the quiz that tells the user which question they’re viewing.

  1.  In *src/app/quiz/quiz.component.html*, before *div.quiz* but after opening* div.quiz-wrapper* tag, paste the code from here [[http://bit.ly/spa-track](http://bit.ly/spa-track)].<br>![](/images/image40.png)**Challenge**: Can you explain to your neighbor what this is doing?
![](../images/24.png)
