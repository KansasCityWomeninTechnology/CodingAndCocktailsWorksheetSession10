### Part 2: Creating a component {#part-2-creating-a-component}

Our app works, but it’s not very exciting. Let’s add some components!

1.  Start in your CLI tool and generate a component named quiz with Angular CLI.Type: ng g component quiz

| Helpful tip: |
| --- |

1.  Let’s add some styles to our app, so it won’t look bland as we develop it.![windows-icon.png](images/image23.png) Windows users you’ll need to click the “raw” button to copy code from github to avoid copying the line numbers with the code![raw.png](images/image32.png)

1.  Copy the CSS styles here [[http://bit.ly/spa-css-a](https://www.google.com/url?q=http://bit.ly/spa-css-a&sa=D&ust=1479686156141000&usg=AFQjCNHxMUSfQXmiQ5XR2tlKbQtZWKetJQ)] &amp; paste into your src/styles.css file.These are global styles that apply to the whole app.
2.  Copy the CSS styles here [[http://bit.ly/spa-css-b](https://www.google.com/url?q=http://bit.ly/spa-css-b&sa=D&ust=1479686156142000&usg=AFQjCNFfXzzZCfus01BRb7a_mtRmYaxCRw)] &amp; paste into your src/app/app.component.css file.These styles apply only to the markup in app.component.html.
3.  Copy the CSS styles here [[http://bit.ly/spa-css-c](https://www.google.com/url?q=http://bit.ly/spa-css-c&sa=D&ust=1479686156143000&usg=AFQjCNH5DXHFCu1alvaRWlZ653U8Vsvs-g)] &amp; paste into src/app/quiz/quiz.component.css.These styles apply only to the markup in quiz.component.html.

| What is this HTML &amp; CSS stuff? |
| --- |

1.  Now that we have styles, let’s add the HTML markup for our templates.

1.  Copy the HTML here [[http://bit.ly/spa-fonts](https://www.google.com/url?q=http://bit.ly/spa-fonts&sa=D&ust=1479686156149000&usg=AFQjCNH8YCrBjvdwcD7BMrDBn9fzQwlVGg)] &amp; paste into your src/index.html file, above the closing &lt;/head&gt; tag.![](images/image36.png)This adds some Google Web Fonts, so we have some pretty fonts in our app.
2.  Let’s add our quiz component html to our app component.Copy the HTML here [[](https://www.google.com/url?q=http://bit.ly/spa-html2&sa=D&ust=1479686156151000&usg=AFQjCNGZdevYNpNeLx_RiM67_8P15RnaRg)[http://bit.ly/spa-html-a](https://www.google.com/url?q=http://bit.ly/spa-html-a&sa=D&ust=1479686156151000&usg=AFQjCNFBfI2S5IjDxl7gZ0gDgCuyNwKGXA)] &amp; paste into src/app/app.component.html.

| ![](images/image24.png) | **Illegal nested table :** Helpful tip:<app-quiz></app-quiz> is the HTML selector for our quiz component. So this tag will be replaced (automagically) by the HTML in our src/app/quiz/quiz.component.html file.Where does <app-quiz> come from? In the Component metadata in our src/app/quiz/quiz.component.ts file, the selector is set to app-quiz.</app-quiz> |
| --- | --- |

1.  Copy the HTML here [[http://bit.ly/spa-html3c](https://www.google.com/url?q=http://bit.ly/spa-html3c&sa=D&ust=1479686156159000&usg=AFQjCNFzyY6FL9lDGS8_gWe9xvXra3sEQw)] &amp; paste into src/app/quiz/quiz.component.html.![](images/image28.png)
2.  Head on over to Chrome to check out how your app looks.

| ![](images/image08.png) | **Illegal nested table :** App doesn’t look like this?Look back through the steps or grab a mentor! |
| --- | --- |