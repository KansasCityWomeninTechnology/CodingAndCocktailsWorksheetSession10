### Part 2: Creating a component

Our app works, but it’s not very exciting. Let’s add some components!

1.  In Git Bash or iTerm2, generate a component named quiz with Angular CLI. Type: `ng g component quiz`

  {% hint style='tip' %}
This creates a _src/app/quiz_ directory with 4 files in it: _html, css, typescript & spec_.  _spec_ files are to write tests (to make sure your code works). We won't be using these tonight so you can ignore this file.
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
   
  2. Paste (use the [keyboard shortcuts](/reference-helpful-keyboard-shortcuts.md)!) the CSS code into your _src/styles.css_ file. These are global styles that apply to the whole app.
  
  3.  Copy these CSS styles:
  
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
   
  4. Paste the CSS code into your *src/app/app.component.css* file. These styles apply only to the markup in _app.component.html_.
  
  5.  Copy these CSS styles:
  
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
   
  6. Paste the CSS code into the *src/app/quiz/quiz.component.css* file. These styles apply only to the markup in _quiz.component.html_.
  
      {% hint style='info' %}
#### What is this HTML & CSS stuff?!
In an effort to keep the project focused on Single Page Applications, we're providing the HTML & CSS code for you to copy/paste.
 
##### New to HTML/CSS? 
Take a minute to read what you pasted.  Try to predict what you might see in the finished product. If you have questions about any of it, or HTML/CSS in general, grab a mentor! 

##### Know HTML/CSS?
Have at it! Customize the HTML/CSS to your liking!
  {% endhint %}

3.  Now that we have styles, let’s add the HTML markup for our templates.

  1.  Copy the HTML code:
  
      ```
      <link href="//fonts.googleapis.com/css?family=Playfair+Display|Raleway" rel="stylesheet">
      ```
   
  2. Paste it into your *src/index.html* file, above the closing &lt;/head&gt; tag. This adds some Google Web Fonts to make the app a bit more visually appealing.
  
      ![](/images/image36.png)
  
  3.  Add the **quiz** component html to the **app** component. Copy the HTML code:
  
      ```
      <div class="quiz-wrapper">
          <h1>{{title}}</h1>
          <app-quiz></app-quiz>
      </div>
      ```
   
  4. Paste it into the *src/app/app.component.html* file.
  
      ![](../images/image24.png)

  5. Copy the HTML code:
  
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

  6. Paste it into the *src/app/quiz/quiz.component.html* file.
  
  ![](/images/image28.png)

4.  Head on over to Chrome to check out how your app looks.

    ![](/images/appOne.png)

  {% hint style='danger' %}
#### App doesn't look like this?
Look back through the steps or grab a mentor!
  {% endhint %}
