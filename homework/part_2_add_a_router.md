### Homework Part 2: Add a New Route

  1. In Git Bash or iTerm2, create a new component called **about**. Type: `ng g component about`.

  2. In Atom, open the _src/app/app-routing.module.ts_ file.

    1. You need to `import` your **About** component for routing, so add that import statement to the top of the file similar to the way the QuizComponent is imported.

    2.  Next, add the **about** route to the `routes` array.

      {% hint style='tip' %}
The format for a route looks like this [replace the _urlpath_ and _MyComponent_ words with your the urlpath you want to define and the component that should be displayed at that path]:

```
{
  path: 'urlpath',
  component: MyComponent
}```

When defining a route, don't include the '/' at the beginning
      {% endhint %}

  3.  Visit your app in Chrome to checkout your new route!  [http://localhost:4200/about](http://localhost:4200/about)

[![](../images/29.png)](http://bit.ly/spa-homework)
