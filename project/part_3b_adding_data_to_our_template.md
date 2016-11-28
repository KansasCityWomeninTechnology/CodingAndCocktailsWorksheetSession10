### Part 3B: Adding Data to Our Template {#part-3b-adding-data-to-our-template}

Now that we have our data ready, let’s wire it up to our component’s template. Open src/app/quiz/quiz.component.html &amp; let’s get to it.

1.  In <span class="ref">&lt;div class=&quot;quiz-wrapper&quot;&gt;</span>, at the top of the file, add an <span class="ref">*ngIf</span> attribute:<br><span class="new">*ngIf=&quot;questions&quot;</span><br>Printed worksheets see: [http://bit.ly/spa-if1](http://bit.ly/spa-if1)![](/images/image04.gif)<span class="ref">*ngIf</span> is an Angular attribute directive that will only render our template IF <span class="ref">this.questions</span> is defined in our component.
2.  In the markup for <span class="ref">&lt;div class=&quot;each-question&quot;&gt;</span>, add the following as an attribute:<br><span class="new">*ngFor=&quot;let question of questions; let i = index;&quot;</span>

  Printed worksheets see: [http://bit.ly/spa-for1](http://bit.ly/spa-for1)![](/images/image17.gif) 
  ![](../images/19.png)
  ![](../images/32.png)
1.  Replace  <span class="ref">question</span> here  with <span class="new">{{question.text}}</span>![](/images/image02.png)This will use the *question’s text* from our data to populate our template.
2.  Let’s loop through our answers. In the <span class="ref">&lt;li&gt;</span> tag, add the following <span class="ref">*ngFor</span> attribute: <span class="new">*ngFor=&quot;let answer of question.answers&quot;</span><br>Printed worksheets see: [http://bit.ly/spa-for2](http://bit.ly/spa-for2)![](/images/image20.gif)
3.  Replace <span class="ref">answer here</span> with <span class="new">{{answer.text}}</span>![](/images/image26.png)
4.  We now have our template rendering questions and answers, but nothing happens when a user selects an answer. Let’s add a *click* event so we can start tracking this.

  1.  In that same <span class="ref">&lt;li&gt;</span> tag, add a <span class="ref">(click)</span> attribute:<span class="new">(click)=&quot;onSelect(answer)&quot;</span><br> 
      ![](/images/image46.png)

      ![](../images/20.png)

   1.  Open *src/app/quiz/quiz.component.ts*. <br>Copy the code here [[http://bit.ly/spa-select](http://bit.ly/spa-select] &amp; paste after the <span class="ref">ngOnInit() {}</span> method.![](/images/image03.png)

    ![](../images/21.png)

Your src/app/quiz/quiz.component.ts file should look like the one here [[http://bit.ly/spa-6_b](http://bit.ly/spa-6_b)].