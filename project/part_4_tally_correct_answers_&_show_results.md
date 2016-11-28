### Part 4: Tally Correct Answers &amp; Show Results {#part-4-tally-correct-answers-show-results}

We now have questions and answers to create a quiz, but at the end of the quiz, the user won’t know how many they answered correctly. Let’s add a counter that keeps track of the correct answers throughout a quiz and displays the results at the end!

1.  Copy the code here [[http://bit.ly/spa-4_1](http://bit.ly/spa-4_1)] &amp; paste into your *src/app/quiz/quiz.component.html* before the final <span class="ref">&lt;/div&gt;</span> tag.![](/images/image16.png)

  ![](/images/22.png)

1.  Open *src/app/quiz/quiz.component.ts*.

  1.  Below <span class="ref">questions: Question[];</span> let’s add 3 new variables and their types: <br><span class="new">correctAnswers: number;currentQuestion</span><br><span class="new">Index: number;</span><br><span class="new">quizIsOver: boolean;</span>![](/images/image35.png)
  2.  Then in ngOnInit, before <span class="ref">this.questions</span>, let’s set default values for these 3 variables:<br><span class="new">this.correctAnswers = 0;</span><br><span class="new">this.currentQuestionIndex = 0;</span><br><span class="new">this.quizIsOver = false;</span>![](/images/image39.png)
![](../images/23.png)

    1. We  need to increment our <span class="ref">correctAnswers</span> variable, every time an answer is correct.<br> In the <span class="ref">onSelect</span> method, within the <span class="ref">if (answer.correct) {...}</span> add: <span class="new">this.correctAnswers++;</span>![Screen Shot 2016-10-08 at 11.51.11 AM.png](/images/image19.png)<br>This will update the value of *correctAnswers* + 1, when the *answer* is *correct*.
  2.  We need to increment <span class="ref">currentQuestionIndex</span>, every time an answer is selected (correct or not).Below <span class="ref">onSelect’s else {...}</span> add: <span class="new">this.currentQuestionIndex++;</span>![Screen Shot 2016-10-08 at 11.54.05 AM.png](/images/image07.png)
  3.  Below <span class="ref">this.currentQuestionIndex++;</span> add: <span class="new">if (this.currentQuestionIndex === this.questions.length) {  this.quizIsOver = true;}</span><br>![Screen Shot 2016-10-07 at 9.49.59 PM.png](/images/image10.png)When the <span class="ref">currentQuestionIndex</span> value is the same as the <span class="ref">questions.length</span> value, <span class="ref">quizIsOver</span> is set to true.

1.  Right now, you see all the quiz questions at once. And even when the results display, the questions/answers are still visible. Let’s add an <span class="ref">*ngIf</span>, so we only see 1 question at a time.

1.  Open src/app/quiz/quiz.component.html. In <span class="ref">&lt;div class=&quot;q-and-a&quot;&gt;</span>, add attribute: <span class="new">*ngIf=&quot;currentQuestionIndex === i&quot;</span> <br>Printed worksheets see: [http://bit.ly/spa-if2](https://www.google.com/url?q=http://bit.ly/spa-if2&sa=D&ust=1479686156253000&usg=AFQjCNGB8a6X4JI9NMTbOP5237p1G--0VA)<br>![](/images/image41.gif)

1.  **BONUS**: Add a tracker to the top of the quiz that tells the user which question they’re viewing.

  1.  In *src/app/quiz/quiz.component.html*, before *div.quiz* but after opening* div.quiz-wrapper* tag, paste the code from here [[http://bit.ly/spa-track](http://bit.ly/spa-track)].<br>![](/images/image40.png)**Challenge**: Can you explain to your neighbor what this is doing?
![](../images/24.png)
