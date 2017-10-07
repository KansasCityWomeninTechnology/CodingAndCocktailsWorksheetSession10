# Part 2: Creating a component

Your app works, but it’s not very exciting. Add some components to it!

1.  In Git Bash or iTerm2, generate a component named quiz with Angular CLI. Type: `ng g component quiz`

  {% hint style='tip' %}
This creates a _src/app/quiz_ directory with 4 files in it: _quiz.component.html_, _quiz.component.css_, _quiz.component.ts_ & _quiz.component.spec.ts_.  _spec_ files are to write tests (to make sure your code works). You won't be using these tonight so you can ignore this spec file.
  {% endhint %}

2.  Next, add some styles to your app, so it won’t look bland as you develop it.

  1.  Copy (check out the [keyboard shortcuts](/reference-helpful-keyboard-shortcuts.md) for help!) these CSS styles:

      ```
      body {
          align-items: center;
          background: #000;
          color: #fff;
          display: flex;
      	  font-family: 'Raleway', sans-serif;
          font-weight: 200;
          height: 100vh;
          justify-content: center;
          margin: 0;
      }

      ul {
          margin: 0;
          padding: 0;
      }
      ```

  2. In Atom, open the _src/styles.css_ file for editing by double clicking on it in the left side project pane.
  
  3. Paste (use the [keyboard shortcuts](/reference-helpful-keyboard-shortcuts.md)!) the CSS code into your _src/styles.css_ file. These are global styles that apply to the whole app.
  
  3. Save the _src/styles.css_ file.

  4.  Copy these CSS styles:

      ```
      .quiz-wrapper {
          max-height: 100vh;
          max-width: 31rem;
      }

      h1 {
          color: #4db6ac;
          float: left;
          font-size: 0.9rem;
          font-style: italic;
          margin: 0;
          padding: 1rem;
      }
      ```

  5. In Atom, open the _src/app/app.component.css_ file for editing and paste the CSS code into your *src/app/app.component.css* file. These styles apply only to the markup in _app.component.html_.
  
  6. Save the _src/app/app.component.css_ file.

  7.  Copy these CSS styles:

      ```
      .question-tracker,
      .results-header {
          color: #ff9800;
          float: right;
          font-size: 0.9rem;
          font-style: italic;
          padding: 1rem;
      }

      .quiz {
          clear: both;
      }

      .question,
      .results {
          background: #111;
          color: #cddc39;
          margin: 0;
          padding: 1rem;
      }

      .question {
          font-family: 'Playfair Display', serif;
          font-size: 2.5rem;
      }

      .answers {
          background: #1f1f1f;
            list-style-position: inside;
            list-style-type: lower-alpha;
      }

      .answers li {
            color: #f06292;
            cursor: pointer;
            font-size: 1.1rem;
            padding: 1rem;
            transition:all 0.5s ease;
      }

      .answers li:hover {
            background: #222;
            color: #ba68c8;
      }

      .results {
            font-family: 'Raleway', sans-serif;
            text-align: center;
      }

      .score {
            color: #f06292;
            font-size: 4rem;
            text-transform: uppercase;
      }

      .result-message {
            font-size: 2.8rem;
      }

      .result-action {
            color: #ba68c8;
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
      }
      ```

  8. In Atom, open the _src/app/quiz/quiz.component.css_ file and paste the CSS code into the file. These styles apply only to the markup in _quiz.component.html_.
  
  9. Save the _src/app/quiz/quiz.component.css_ file.
  
  10. In Google chrome, take a look at your app now.  You'll see the styles have changed and the page background is now black along with some other styling changes.
  
      ![](/images/newStyles.png)

      {% hint style='info' %}
  #### What is this HTML & CSS stuff?!
  In an effort to keep the project focused on Single Page Applications, we're providing the HTML & CSS code for you to copy/paste. Keep an eye out to join us for our HTML & CSS sessions if you're interested in learning more!

  ##### New to HTML/CSS?
  Take a minute to read what you pasted.  Try to predict what you might see in the finished product. If you have questions about any of it, or HTML/CSS in general, grab a mentor!

  ##### Know HTML/CSS?
  Have at it! Customize the HTML/CSS to your liking!
      {% endhint %}

3.  Now that you have styles, add the HTML markup for your templates.

  1.  Copy this HTML code:

      ```
      <link href="//fonts.googleapis.com/css?family=Playfair+Display|Raleway" rel="stylesheet">
      ```

  2. In Atom, open the *src/index.html* file by double clicking on it in the left side project pane.
  
  3. Find the `</head>` tag. This tag closes out the head section of your HTML document where some information about the HTML document is usually provided. 
  
  4. Place your cursor at the end of the line that looks like `<link rel="icon" type="image/x-icon" href="favicon.ico">` and press enter to move to a new line.  Your cursor should now be between that `link` tag and the `</head>` tag.
  
  5. Paste the HTML code from above on this new line. The code you're pasting in adds some Google Web Fonts to make the app a bit more visually appealing.

      ![](/images/image36.png)

  6.  Add the **quiz** component html to the **app** component. Copy the HTML code:

      ```
      {% raw %}<div class="quiz-wrapper">
          <h1>{{title}}</h1>
          <router-outlet></router-outlet>
      </div>{% endraw %}
      ```

  4. In Atom, open the *src/app/app.component.html* file. Delete all of the HTML code from the file and paste in the code you copied in the previous step.

        ![](/images/quizComponentHTML.png)

  5. Copy the HTML code below:

        ```
        <div class="quiz-wrapper">

          <div class="quiz">

            <div class="each-question">
              <div class="q-and-a">
                <h3 class="question">question here</h3>

                <ul class="answers">
                  <li>answer here</li>
                </ul>
              </div>
            </div>

          </div>

        </div>
        ```

  6. Delete all the code in the *src/app/quiz/quiz.component.html* file and paste the copied HTML into the file.

        ![](/images/image28.png)
        
  7. Save the *src/app/quiz/quiz.component.html* file.

4.  Head on over to Chrome to check out how your app looks.

   _It probably doesn't look like this:_

    ![](/images/appOne.png)

  We need to add a default route, so that it loads our Quiz Component's HTML & CSS.

5. In Atom, open _src/app/app-routing.module.ts_.

  1. We need to import our Quiz Component. Add a new line below `import { Routes, RouterModule } from '@angular/router';` and type: `import { QuizComponent } from './quiz/quiz.component';`

  2. Place your cursor between the brackets `[]` in `const routes: Routes = [];` & hit enter to create a new line between the brackets.

  3. On this new line type: {}

  4. Place your cursor between the curly braces & hit enter to create another new line.

  3. Hit the tab key & type:

    ```
    path: '',
    component: QuizComponent
    ```

    TODO: IMAGE OR SOMETHING LIKE _Code should look like this:_
    ```
    const routes: Routes = [
      {
        path: '',
        component: QuizComponent
      }
    ];
    ```

    4. Now go look at your app in Chrome.

      ![](/images/appOne.png)

    {% hint style='danger' %}
    #### App doesn't look like this?
    Look back through the steps or grab a mentor!
    {% endhint %}
