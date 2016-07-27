# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    A router primarly declares a route and a sub-route. The route gets data through
    the model.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    import Ember from 'ember';
    import config from './config/environment';

    const Router = Ember.Router.extend({
      location: config.locationType,
    });

    Router.map(function () {
    this.route('campus', function() {
      this.route('boston');    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
<h4>{{#link-to 'campus.boston' }}about engineering{{/link-to}}</h4>    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first example exhibits a sub path of products through a traditional syntax
    with a function call while the other does not.
    The second defines the sub path through part of the url which the route will
    parse.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    export default Ember.Route.extend({
        model: function(){
          return [
            {
              id: 123,
              name: 'The Ember Strikes Back',
              director: 'Yehuda Katz',
            },    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    One way is to use an #each bearing model data.
    {{#each model as |list|}}
      {{listr-list list=list}}
    {{/each}}
    ```
