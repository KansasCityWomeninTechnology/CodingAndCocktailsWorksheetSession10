### Part 6: Creating a Service & Fetching Data

You have your component set-up to display trivia questions and answers, but you only have a couple hardcoded questions & answers. Next you'll use an API to populate your quiz questions and possible answers.

{% hint style='info' %}
A service is just one piece of your larger application. Services are used to:
* share data or logic across multiple components of an application to avoid code duplication
* encapsulate external interactions (like with our API).
{% endhint %}

1. First, use **Angular CLI** to generate a service named **quiz** within the _quiz_ directory. In Git Bash or iTerm2, type: `ng g service quiz/quiz`

  {% hint style='tip' %}
This creates two files in your _src/app/quiz_ directory:
  * _quiz.service.ts_ and
  * _quiz.service.spec.ts_
  
You won't be adding any tests tonight, so you can ignore the _quiz.service.spec.ts_ file.
  {% endhint %}

2.  In Atom, open the _src/app/quiz/quiz.service.ts_ file. 

# TODO: Update this section below
  You need to import some methods from the **HTTP Module & RxJS** (**Angular CLI** installed both of these for us so we can simply import to use them). 
  
3. Place your cursor at the end of the first line of the file that reads `import { Injectable } from '@angular/core';` and press return.

4. Type: `import { Http, Response } from '@angular/http';`

5. Press return to move to a new line and then type`import 'rxjs/add/operator/map';`

6. On the line that starts with `constructor()`, place your cursor in between the parenthesis and type: `private http: Http`

  ![](/images/image27.png)

  This creates an instance of the `Http` service that you imported and assigns it to `http`. It’s private because you don’t want to access it from outside the `QuizService` class.

7.  Now, you’re going to add your API request to **//cocktail-trivia-api.herokuapp.com/api/sample**. Copy the code below:

  ```
  getQuestions() {
    return this.http.get('//cocktail-trivia-api.herokuapp.com/api/sample')
      .map((res: Response) => res.json());
  }
  ```

8. Paste the code in the _src/app/quiz/quiz.service.ts_ file just below the `constructor(private http: Http) { }` line

  ![](../images/26.png)

9.  Open *src/app/quiz/quiz.component.ts*.

  1.  You need to import the `QuizService`, so that you can use it. Add the following to the list of your other imports: `import { QuizService } from './quiz.service';`
  
  2.  In our `Component` metadata, you need to add `QuizService` as a provider. Add a comma & a new line after `styleUrls: ['./quiz.component.css']` and add:`providers: [QuizService]`
  
  ![](/images/image22.png)
  
3.  In the parenthesis for `constructor() { }` add:`private quizService: QuizService`

  ![](/images/image48.png)
  
  Now, you can access the `QuizService methods` via `this.quizService`.
  
4.  Replace `this.questions = [...];` with: `this.quizService.getQuestions()  .subscribe(questions =< this.questions = questions);`

![](/images/image13.png)

![](../images/27.png)