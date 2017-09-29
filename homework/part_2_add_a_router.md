### Homework Part 2: Add a router 

It is recommended to watch this video [[http://bit.ly/router-video](http://bit.ly/router-video)] (sign-up for free account to view) or read this article [[http://bit.ly/angular2-routing](http://bit.ly/angular2-routing)] to see how routers work in Angular & how to configure them.

1.  Create a new component named **about**.

2.  Create a new file in *src/app* and name it** app.routes.ts**

3.  In this new file, you need to import a couple things from the Router module.

  At the top of the file, type: `import { Routes, RouterModule } from '@angular/router';`
  
4.  Next, set your variable that will hold your routes. Type: `const routes: Routes = [];` 

  This sets a **constant** variable named `routes` [of imported type `Routes`] to an empty array. You’ll add your routes to this array.
  
5.  In between the opening and closing square brackets of your array, add 2 routes:

  1. '' that loads your `QuizComponent` [this is the root or homepage path '/']
  
  2.  `'about'` that loads your new `AboutComponent` [this will load for the path '/about']
  
  {% hint style='tip' %}
The format for a route looks like this [replace the italicized words with your own]:
`{path: '_urlpath_',component: _MyComponent_}`

When defining a route, don't include the '/' at the beginning
  {% endhint %}

1.  You need to `import` your 2 components, so add those 2 import statements to the top of the file.

2.  Next, export your routes, so at the bottom of *app.routes.ts*, type: `export const QuizAppRoutes = RouterModule.forRoot(routes);`

3.  Open the *src/app/app.module.ts* file & add an `import`. Import `QuizAppRoutes` from *app.routes.ts* [hint: that needs minor modifications to make that the actual import statement.]

4.  You also need to add `QuizAppRoutes` in this file’s `@NgModule imports`.

5.  Last, but not least, you need to define where your router will display the relevant component.

  In the *src/app/app.component.html* file, replace `<app-quiz></app-quiz>` with `<router-outlet></router-outlet>`
  
6.  Visit your app in Chrome to checkout your routes! [http://localhost:4200/](http://localhost:4200/) & [http://localhost:4200/about](http://localhost:4200/about)

[![](../images/29.png)](http://bit.ly/spa-homework)