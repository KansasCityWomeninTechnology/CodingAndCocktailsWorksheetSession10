### Part 6: Creating a Service & Fetching Data

You have your component set-up to display trivia questions and answers, but you only have a couple hardcoded questions & answers. Next you'll create a service to use an API to populate your quiz questions and possible answers.

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

2. You'll use an **HTTPClient Module** that Angular provides, but you need to tell Angular that you want to use it. In Atom, open the _app.module.ts_ file.

  1. Add a new blank line below the `import {NgModule} from '@angular/core';` line & type:
  `import { HttpClientModule } from '@angular/common/http';`

  2. In the same file, look for `imports` section within the parameters passed to `@NgModule`. Add a comma after `AppRoutingModule` & add a new line. On this new line, type: `HttpClientModule`

2.  In Atom, open the _src/app/quiz/quiz.service.ts_ file.

    You'll need to import a method from the **HttpClientModule** and your **Question** model.

    1. Place your cursor at the end of the first line of the file that reads `import { Injectable } from '@angular/core';` and press return.

    2. Type: `import { HttpClient } from '@angular/common/http';`

    3. Press return to move to a new line and then type: `import { Question } from './quiz.model';`

    4. In between the parenthesis of the `constructor()` code, type: `private http: HttpClient`
    
      ![](/images/httpClient.png)

      {% hint style='tip' %}
This creates an instance of the `HttpClient` service that you imported and assigns it to `http`. It’s private because you don’t want to access it from outside the `QuizService` class.
      {% endhint %}

    5. Now, you’re going to add your API request to **//cocktail-trivia-api.herokuapp.com/api/sample**. Copy the code below:

    ```
    getQuestions(): Observable<Question[]> { 
      return this.http.get<Question[]>('//cocktail-trivia-api.herokuapp.com/api/sample'); 
    }
    ```

    6. Paste the code in the _src/app/quiz/quiz.service.ts_ file just below the `constructor(private http: Http) { }` line

    TODO: UPDATE IMAGE
    ![](../images/26.png)

9.  In Atom, open the _src/app/quiz/quiz.component.ts_ file.

  1.  You need to import the `QuizService`, so that you can use it. Add the following to the list of your other imports: `import { QuizService } from './quiz.service';`

  2.  In our `Component` metadata, you need to add `QuizService` as a provider. Add a comma & a new line after `styleUrls: ['./quiz.component.css']` and add:`providers: [QuizService]`

  ![](/images/image22.png)

  3. In the parenthesis for `constructor() { }` add:`private quizService: QuizService`

  ![](/images/image48.png)

  Now, you can access the `QuizService methods` via `this.quizService`.

4.  Replace `this.questions = [...];` with:
    ```
    this.quizService.getQuestions()
      .subscribe(questions => this.questions = questions);
    ```

    ![](/images/image13.png)

![](../images/27.png)
