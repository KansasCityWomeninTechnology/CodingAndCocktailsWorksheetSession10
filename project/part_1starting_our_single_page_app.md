# Part 1: Starting your Single Page App

### App Foundation
Start with creating your app’s foundation. Open Git Bash (Windows) or iTerm2 (Mac) and rock &amp; roll.

1.  In Git Bash or iTerm2, Navigate to your CodingAndCocktails folder. Type: `cd ~/CodingAndCocktails`

 Then press **enter**. You will need to press enter after any command you enter in the command line.

  {% hint style='tip' %}
#### Command line woes?
  - Your home directory is:
    - Mac: `/users/<yourUsername>`
    - Windows: `C:/Users/<yourUsername>`
  - Command to change folders: `cd <folderToGoTo>`
  - Command to make a folder: `mkdir <newFolder>`
  - You can also use **~** as a shortcut in your CLI for your home directory: ``cd ~``
</br>
</br>
  Revisit the command line worksheet from March:
  [bit.ly/CnCMarWork](http://bit.ly/CnCMarWork)
  {% endhint %}

2.  In Git Bash or iTerm2, use Angular CLI to scaffold the project. Type: `ng new trivia`

3.  In Git Bash or iTerm2, Change the directory to the new one Angular CLI created for you. Type: `cd trivia`

4.  In Git Bash or iTerm2, run your new app. Type: `ng serve`

  {% hint style='info' %}
This command will:

1. Compile your TypeScript files into JavaScript
</br>
2. Start a local server on our computer so you can view your project prior to making it live on the internet
</br>
3. Watch your project files for changes so that when one of them changes it will automatically reload in the browser for you and avoid the step of having to push the refresh button to see every update you make.
  {% endhint %}
  
  {% hint style='danger' %}
![images/windows-icon.png](/images/windows-icon.png)
Windows will take more time for the ng serve process and for the automatic reload in the browser (upon file changes), unless you are running as admin. If you don’t recall doing this earlier, see tips [here](http://bit.ly/angular-cli-windows) to make it run faster.
  {% endhint %}

5.  In Google Chrome, navigate to [http://localhost:4200](http://localhost:4200) to see your working (basic) app.

  {% hint style='tip' %}
In iTerm2 (mac), open a new tab or in Git Bash (windows), open a new window to be ready for the next CLI commands.  You'll want to leave `ng serve` running in your CLI tool to see the live updates as you progress through the project.
  {% endhint %}

### Make a Change

Make some updates to the app to see the live reload we get from `ng serve`! Remember the `ng serve` command watches for changes to your project files and automatically refreshes the browser for you so you don’t have to.  This is called “live reload.”

1.  Open Atom via the command line

  {% hint style='danger' %}
**Cloud9 users:** Skip this step.
  {% endhint %}

  Type: `atom .`
  
  {% hint style='danger' %}
Command not found

If Atom doesn't open (but you know it's installed), your system likely doesn't recognize the `atom` command.

You can configure your system to recognize the command (ask a mentor for help) or you can follow these steps to open it manually:
  1. From your applications or start menu, open Atom
  2. In Atom: File >> Open... (Mac) or Open Folder... (Windows)
  3. Open the _trivia-api_ folder
  4. Click the Open button
  {% endhint %}

2. In Atom, in the left side project pane, click on the arrow next to _src_ to expand the folder.

3. Next, do the same thing next to the _app_ folder to expand it.

4. Double click on the _app.component.ts_ file inside that _app_ folder to open it in the right side editing pane.
  
5.  Edit the `title` variable to whatever text you want (like: have a cocktail!)

  {% hint style='info' %}
This `title` will end up being the title of your trivia app.
  {% endhint %} 
  
  ![](/images/image11.gif)

6.  Save your file & go back to the tab in Chrome that has your app running. You should see your updated text!

    ![](/images/appUpdate.gif)

##### Nice work! Take a break and grab another drink, you've earned it! 