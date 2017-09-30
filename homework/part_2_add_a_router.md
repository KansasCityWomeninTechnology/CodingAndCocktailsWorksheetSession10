### Homework Part 2: Add a New Route

<!-- It is recommended to watch this video [[http://bit.ly/router-video](http://bit.ly/router-video)] (sign-up for free account to view) or read this article [[http://bit.ly/angular2-routing](http://bit.ly/angular2-routing)] to see how routers work in Angular & how to configure them. -->

  1. Create a new component named **about**.

  2. In Atom, open the _src/app/app-routing.module.ts_ file.

    1. You need to `import` your **About** component, so add that import statement to the top of the file.

    2.  Next, add the **about** route to the `routes` array.

      {% hint style='tip' %}
      The format for a route looks like this [replace the italicized words with your own]:
      `{path: '_urlpath_',component: _MyComponent_}`

      When defining a route, don't include the '/' at the beginning
      {% endhint %}

    <!-- This sets a **constant** variable named `routes` [of imported type `Routes`] to an empty array. You’ll add your routes to this array. -->

    <!-- 1. '' that loads your `QuizComponent` [this is the root or homepage path '/']

    2.  `'about'` that loads your new `AboutComponent` [this will load for the path '/about'] -->


  3.  Visit your app in Chrome to checkout your new route!  [http://localhost:4200/about](http://localhost:4200/about)

[![](../images/29.png)](http://bit.ly/spa-homework)
