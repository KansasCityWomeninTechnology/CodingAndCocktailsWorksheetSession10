### Homework Part 1: Git - Deploy App to GitHub Pages 

Angular CLI initialized a git repository for you in your source folder. Angular CLI provides us a command to deploy our app to GitHub Pages.

1.  Open your Git Bash or iTerm2 & check git.  Type: `git status`.

   You should see several files listed as `modified:` under the heading "Changes not staged for commit:" 

2. Stage your files to tell git what files you want to add. Type: `git add .`

   ![](/images/image45.png)
   
3. Check your status again. Type `git status`.

   You should see your files now listed under the heading "Changes to be committed:"
   
4.  Commit all your files. Type: `git commit -m "Trivia App Initial Development"`

   ![](/images/image18.png)
   
5.  Deploy your app to GitHub Pages. Type: `ng github-pages:deploy --message "Add your own message here"`

   ![](/images/image49.png)
   
   It may prompt you to generate a token on GitHub. Follow the instructions as provided in your CLI tool. 

   ![windows-icon.png](/images/windows-icon.png) This is another command that will run faster if you run Git Bash as admin. 

6.  View your App from Chrome or from your phone!When the deployment to GitHub Pages is completed, it will provide the URL for your app.Format of the URL should be something like https://username.github.io/trivia