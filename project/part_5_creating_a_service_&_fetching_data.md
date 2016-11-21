### Part 5: Creating a Service &amp; Fetching Data {#part-5-creating-a-service-fetching-data}

We have our component set-up to display trivia questions and answers, but we only have a couple hardcoded questions &amp; answers. Let’s use an API to populate our quiz questions and possible answers.

A service is just one piece of our larger application. Services are used to:

*   share data or logic across multiple components of an application to avoid code duplication or
*   to encapsulate external interactions (like with our API).


1.  First, use *Angular CLI* to generate a service named *quiz* within the *quiz* directory. Open your CLI tool.Type: <span class="cmd"> ng g service quiz/quiz</span>

       ![](../images/25.png)

1.  Open *src/app/quiz/quiz.service.ts*. We need to <span class="ref">import</span> some methods from the *HTTP Module &amp; RxJS* [*Angular CLI* installed both of these for us so we can simply import to use them]. Add these imports below the *@angular/core import*:<br><span class="new">import { Http, Response } from &#039;@angular/http&#039;;</span><br><span class="new">import &#039;rxjs/add/operator/map&#039;;</span><br>
2.  In the parenthesis for constructor(), add:<br><span class="new">private http: Http</span>![](/images/image27.png)<br>This creates an instance of the <span class="ref">Http</span> service that we imported and assigns it to <span class="ref">http</span>. It’s private because we don’t want to access it from outside the <span class="ref">QuizService</span> class.
3.  Now, we’re going to add our API request to **//cocktail-trivia-api.herokuapp.com/api/sample**.<br>Copy the code from here [[http://bit.ly/spa-http](https://www.google.com/url?q=http://bit.ly/spa-http&sa=D&ust=1479686156271000&usg=AFQjCNFQxlhCBv8eVfsRAPVhgJ-Lu0ESzg)] &amp; paste below <span class="ref">constructor(private http: Http) { }</span>
![](../images/26.png)

1.  Open *src/app/quiz/quiz.component.ts*.

  1.  We need to import the <span class="ref">QuizService</span>, so that we can use it. Add the following to the list of your other imports: <span class="new">import { QuizService } from &#039;./quiz.service&#039;;</span>
  2.  In our <span class="ref">Component</span> metadata, we need to add <span class="ref">QuizService</span> as a provider.<br>Add a comma &amp; a new line after <span class="ref">styleUrls: [&#039;./quiz.component.css&#039;]</span> and add:<br><span class="new">providers: [QuizService]</span>![](/images/image22.png)
3.  In the parenthesis for <span class="ref">constructor() { }</span> add:<br><span class="new">private quizService: QuizService</span>![](/images/image48.png)Now, we can access the <span class="ref">QuizService methods</span> via <span class="ref">this.quizService</span>.
4.  Replace <span class="ref">this.questions = [...];</span> with: <span class="new">this.quizService.getQuestions()  .subscribe(questions =&gt; this.questions = questions);</span>![](/images/image13.png)
![](../images/27.png)