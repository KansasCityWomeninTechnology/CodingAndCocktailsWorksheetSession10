### Part 1: Starting our Single Page App {#part-1-starting-our-single-page-app}

Let’s start with creating our app’s foundation. Open Git Bash (Windows) or iTerm2 (Mac) and rock &amp; roll.

1.  Navigate to your CodingAndCocktails folder: <span class="cmd">cd &lt;your home directory&gt;/CodingAndCocktails</span>

| Command line woes?![](images/image42.png) |
| --- |

1.  Use Angular CLI to scaffold the project for us. Type: ng new trivia
2.  Change the directory to the new one Angular CLI created for us. Type: cd trivia
3.  Let’s run our new app. Type: ng serveThis command will:

1.  Compile our TypeScript files into JavaScript
2.  Start a local server on our computer so we can view our project prior to making it live on the internet
3.  Watch our project files for changes so that when one of them changes it will automatically reload in the broswer for us and avoid the step of us having to push the refresh button to see every update we make.

![windows-icon.png](images/image23.png) Windows will take more time for the ng serve process and for the automatic reload in the browser (upon file changes), unless you are running as admin. If you don’t recall doing this earlier, see tips here [[http://bit.ly/angular-cli-windows](https://www.google.com/url?q=http://bit.ly/angular-cli-windows&sa=D&ust=1479686156114000&usg=AFQjCNFOZrCt-MVLSFqv8qURGWOdFF7wgw)] to make it run faster.

1.  In Chrome, visit the URL [http://localhost:4200](https://www.google.com/url?q=http://localhost:4200&sa=D&ust=1479686156115000&usg=AFQjCNEJiKiFfCCtcbWB6aGjv8uib0saQg) to see your working (basic) app.

| Helpful tips: |
| --- |

1.  Open your trivia folder in SublimeText.  Let’s make some updates to the app to see the live reload we get from ng serve! Remember the ng serve command watches for changes to our project files and automatically refreshes the browser for us so we don’t have to.  This is called “live reload.”
2.  Open the src/app/app.component.ts file in SublimeText.
3.  Edit the title variable to whatever text you want (like: have a cocktail!)Note: This title will end up being the title of your trivia app.Printed worksheets see: [http://bit.ly/spa-1a](https://www.google.com/url?q=http://bit.ly/spa-1a&sa=D&ust=1479686156127000&usg=AFQjCNFZbhIX5xt0vrxMTlkS7jZgODogHA)![](images/image11.gif)
4.  Save your file &amp; go back to the tab in Chrome that has your app running. You should see your updated text!Printed worksheets see: [http://bit.ly/spa-title](https://www.google.com/url?q=http://bit.ly/spa-title&sa=D&ust=1479686156130000&usg=AFQjCNH4q5UVvvk-IYQyhprFzPLMb0sDBg)

| ![](images/image06.gif) | **Illegal nested table :** Nice work!Take a break and grab another drink.You’ve earned it! |
| --- | --- |