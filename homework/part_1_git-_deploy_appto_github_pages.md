### Part 1: Git - Deploy App to GitHub Pages {#part-1-git-deploy-app-to-github-pages}

Angular CLI initialized a git repository for you in your source folder. Open your CLI tool &amp; check git by running git status. Angular CLI provides us a command to deploy our app to GitHub Pages.

1.  Add all your files to git. Type: <span class="cmd">git add .</span><br>![](/images/image45.png)
2.  Commit all your files. Type: <span class="cmd">git commit -m &quot;Add your own message here&quot;</span>![](/images/image18.png)
3.  Deploy your app to GitHub Pages.

| Type: ng github-pages:deploy --message &quot;Add your own message here&quot;![](images/image49.png)It may prompt you to generate a token on GitHub. Follow the instructions as provided in your CLI tool. |  | ![windows-icon.png](images/image23.png) This is another command that will run faster if you run Git Bash as admin. |
| --- | --- | --- |

1.  View your App from Chrome or from your phone!When the deployment to GitHub Pages is completed, it will provide the URL for your app.Format of the URL should be something like https://username.github.io/trivia