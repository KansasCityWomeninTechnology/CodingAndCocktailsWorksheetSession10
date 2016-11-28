### Part 2: Add a router {#part-2-add-a-router}

It is recommended to watch this video [[http://bit.ly/router-video](https://www.google.com/url?q=http://bit.ly/router-video&sa=D&ust=1479686156301000&usg=AFQjCNFD5AQc0ycAzgtg0dq3pj6SfkbCiw)] (sign-up for free account to view) or read this article [[http://bit.ly/angular2-routing](https://www.google.com/url?q=http://bit.ly/angular2-routing&sa=D&ust=1479686156302000&usg=AFQjCNFl00rr7xlaObQwx_CAzr1oN3YYig)] to see how routers work in Angular 2 &amp; how to configure them.

1.  Create a new component named **about**.
2.  Create a new file in *src/app* and name it** app.routes.ts**
3.  In this new file, we need to import a couple things from the Router module.<br>Add: <span class="new">import { Routes, RouterModule } from &#039;@angular/router&#039;;</span>
4.  Now we need to set our variable that will hold our routes. Add: <span class="new">const routes: Routes = [];</span> This sets a *constant* variable named <span class="ref">routes</span> [of imported type <span class="ref">Routes</span>] to an empty array. We’ll add our routes to this array.
5.  In your array, add 2 routes:

  1.  <span class="ref">&#039;&#039;</span> that loads our <span class="ref">QuizComponent</span> [this is the root or homepage path &#039;/&#039;]
  2.  <span class="ref">&#039;about&#039;</span> that loads our new <span class="ref">AboutComponent</span> [this will load for the path &#039;/about&#039;]

  ![](../images/28.png)

1.  We need to <span class="ref">import</span> our 2 components, so add those 2 import statements to the top of the file.
2.  Now we need to export our routes, so at the bottom of *app.routes.ts*, add this: <br><span class="new">export const QuizAppRoutes = RouterModule.forRoot(routes);</span>
3.  Open the *src/app/app.module.ts* file &amp; add an <span class="ref">import</span>. Import <span class="ref">QuizAppRoutes</span> from *app.routes.ts* [hint: that needs minor modifications to make that the actual import statement.]
4.  We also need to add <span class="ref">QuizAppRoutes</span> in this file’s <span class="ref">@NgModule imports</span>.
5.  Last, but not least, we need to define where our router will display the relevant component.<br>In *src/app/app.component.html*, replace <span class="ref">&lt;app-quiz&gt;&lt;/app-quiz&gt;</span> with <span class="new">&lt;router-outlet&gt;&lt;/router-outlet&gt;</span>
6.  Visit your app in Chrome to checkout your routes! [http://localhost:4200/](http://localhost:4200/) &amp; [http://localhost:4200/about](http://localhost:4200/about)

[![](../images/29.png)](http://bit.ly/spa-homework)