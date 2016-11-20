### Part 3B: Adding Data to Our Template {#part-3b-adding-data-to-our-template}

Now that we have our data ready, let’s wire it up to our component’s template. Open src/app/quiz/quiz.component.html &amp; let’s get to it.

1.  In &lt;div class=&quot;quiz-wrapper&quot;&gt;, at the top of the file, add an *ngIf attribute:*ngIf=&quot;questions&quot;Printed worksheets see: [http://bit.ly/spa-if1](https://www.google.com/url?q=http://bit.ly/spa-if1&sa=D&ust=1479686156199000&usg=AFQjCNF1VNH8SanAHn-CLp-oB9roOPJtjw)![](images/image04.gif)*ngIf is an Angular attribute directive that will only render our template IF this.questions is defined in our component.
2.  In the markup for &lt;div class=&quot;each-question&quot;&gt;, add the following as an attribute:*ngFor=&quot;let question of questions; let i = index;&quot;

| Printed worksheets see: [http://bit.ly/spa-for1](https://www.google.com/url?q=http://bit.ly/spa-for1&sa=D&ust=1479686156203000&usg=AFQjCNHirza2RuAOGQN3dkV1mJZomzDvDw)![](images/image17.gif) | **Illegal nested table :** Helpful tip:To help make the code easier to read, I start each attribute on it’s own line [see the gif above to see that in action]. |
| --- | --- |

| What does this code do? |
| --- |

1.  Replace  question here  with {{question.text}}![](images/image02.png)This will use the question’s text from our data to populate our template.
2.  Let’s loop through our answers. In the &lt;li&gt; tag, add the following *ngFor attribute:*ngFor=&quot;let answer of question.answers&quot;Printed worksheets see: [http://bit.ly/spa-for2](https://www.google.com/url?q=http://bit.ly/spa-for2&sa=D&ust=1479686156215000&usg=AFQjCNENq98ObzKMiqfy3beffZH2KTbG8w)![](images/image20.gif)
3.  Replace answer here with {{answer.text}}![](images/image26.png)
4.  We now have our template rendering questions and answers, but nothing happens when a user selects an answer. Let’s add a click event so we can start tracking this.

1.  In that same &lt;li&gt; tag, add a (click) attribute:(click)=&quot;onSelect(answer)&quot;![](images/image46.png)

| What does this code do? |
| --- |

1.  Open src/app/quiz/quiz.component.ts.Copy the code here [[http://bit.ly/spa-select](https://www.google.com/url?q=http://bit.ly/spa-select&sa=D&ust=1479686156223000&usg=AFQjCNEvNwL_At6vwPb94MFqI0KQJKUxrw)] &amp; paste after the ngOnInit() {} method.![](images/image03.png)

| What does this code do? |
| --- |

        ![check.png](images/image30.png) Your src/app/quiz/quiz.component.ts file should look like the one here [[http://bit.ly/spa-6_b](https://www.google.com/url?q=http://bit.ly/spa-6_b&sa=D&ust=1479686156231000&usg=AFQjCNFKnt3ebjBIOTFy1C5E9uIs4q-3fg)].