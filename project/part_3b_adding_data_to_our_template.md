### Part 4: Adding Data to Your Template

Now that you have your data ready, wire it up to your component’s template.

1.  In Atom, open _src/app/quiz/quiz.component.html_.

2. In the `<div class="quiz-wrapper">` HTML element at the top of the file, place your cursor directly before the `>` to add add an `*ngIf` attribute.  Type: `*ngIf="questions"`

  ![](/images/image04.gif)

  {% hint style='info' %}
`*ngIf` is an Angular attribute directive that will only render our template **IF** `this.questions` is defined in our component because we set it to `"questions"`.
  {% endhint %}
  
3.  In the HTM element `<div class="each-question">;`, place your cursor directly in front of the `>`, add a space and then type the following to add an attribute: `*ngFor="let question of questions; let i = index;";`

  ![](/images/image17.gif)
  
  {% hint style='tip' %}
To help make the code easier to read, the example above starts each attribute on it's own line.
  {% endhint %}

  {% hint style='info' %}
### What does this code do?

This is an `*ngFor` directive that will repeat the HTML markup (including the `div` HTML element with the class `each-question`) for every question in your components `this.questions` array.
</br>
It also sets a variable maned `i` to `index`.  This helps to keep track of what question is currently bein rendered in the template by giving you the `index` of that `question`.  **Question 1 is Index 0. Question 2 is Index 1.** This will come into play later in the tutorial.
  {% endhint %}
  
4.  In the `<h3 class="question">` HTML element, replace the "question here" text with `{{question.text}}`

  ![](/images/image02.png)
  
  This will use the *question’s text* from your data to populate your HTML template.
  
5.  Next, loop through your answers. In the <span class="ref">&lt;li&gt;</span> tag, add the following <span class="ref">*ngFor</span> attribute: <span class="new">*ngFor=&quot;let answer of question.answers&quot;</span><br>Printed worksheets see: [http://bit.ly/spa-for2](http://bit.ly/spa-for2)![](/images/image20.gif)
3.  Replace <span class="ref">answer here</span> with <span class="new">{{answer.text}}</span>![](/images/image26.png)
4.  We now have our template rendering questions and answers, but nothing happens when a user selects an answer. Let’s add a *click* event so we can start tracking this.

  1.  In that same <span class="ref">&lt;li&gt;</span> tag, add a <span class="ref">(click)</span> attribute:<span class="new">(click)=&quot;onSelect(answer)&quot;</span><br> 
      ![](/images/image46.png)

      ![](../images/20.png)

   1.  Open *src/app/quiz/quiz.component.ts*. <br>Copy the code here [[http://bit.ly/spa-select](http://bit.ly/spa-select] &amp; paste after the <span class="ref">ngOnInit() {}</span> method.![](/images/image03.png)

    ![](../images/21.png)

Your src/app/quiz/quiz.component.ts file should look like the one here [[http://bit.ly/spa-6_b](http://bit.ly/spa-6_b)].