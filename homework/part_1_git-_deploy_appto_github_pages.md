### Homework Part 1: Git - Deploy App to GitHub Pages 

Angular CLI initialized a git repository for you in your source folder. Angular CLI provides us a command to deploy our app to GitHub Pages.

1. Make sure you have created your GitHub account from [the tools setup](https://codingandcocktailskc.gitbooks.io/coding-cocktails-the-tools/content/user-accounts---github-slack--codecademy.html) and are logged in to [https://github.com](https://github.com/) in Google Chrome.

2. Create a new repository named **trivia** on github.com.

  1. In Google chrome, navigate to [https://github.com](https://github.com/)
  
  2. In the upper-right corner, click **+**, and then click **New repository**.

    {% hint style='danger' %}
Make sure **Initialize this repository with a README** is **unchecked**.

![](/images/no-readme.PNG)
  {% endhint %}

6. You must connect the repository from GitHub (on the internet) to this repository you now have locally on your computer. This is called adding a remote repository. 

  {% hint style='tip' %}
For more information on working with remotes read [Git Basics - Working with Remotes from the Pro Git book](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
  {% endhint %}

  1. In Google Chrome on the GitHub site make sure you have your `trivia` repository open.
  
  2. Click on the clipboard icon to copy the URL.
  
     ![](/images/gitClone.png)

  3. In Git Bash or iTerm2, type the following to add the remote:
  
    {% label %}Git Bash/iTerm2{% endlabel %}
    ```
    git remote add origin https://github.com/<your_github_username>/trivia.git
    ```
    Replace the git URL with the URL you copied from the GitHub site in step 6.i. above.

7. Check which directories/files are unstaged (that Git doesn't yet know about). Type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git status
  ```
  
  Your files should display under a header of "Untracked files:" and should be red in color.

8. Stage the files so Git knows which files to deal with.  In this case we want all of them so we just add all the files in the current directory. The current directory can be referenced as: `.`.  Type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git add .
  ```

9. Check to ensure all of your files are staged & ready to be committed.

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git status
  ```
  
  Now, your files should display under a header of "Changes to be committed:" and should be green in color.

10. Commit the files so Git understands what group of changes to deal with.  Feel free to change the commit message (the part in the quotation marks) if you'd like!

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git commit -m "Mom, look, my first API!"
  ```

11. Push these changes up to the GitHub website (the origin remote you created in step 6) and set the upstream (`-u`) this is the the gatekeeper of the project or the source of truth to which you wish to contribute to) to the remote's `master` branch. 

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git push -u origin master
  ```
  
12. Your API now exists on GitHub!



























Open your Git Bash or iTerm2 & check git.  Type: `git status`.

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