this guide adapted from: https://guides.emberjs.com/v2.14.0/getting-started/quick-start/

# Ember

Ember is a front-end JavaScript framework (based on the model-view-viewmodel[MVVM]) that provides a large amount of easy to use features for developers such as handlebars and route generation.

An alternative to Ember would be any single page front end framework, ie angular.

Some examples of Ember in the wild:

* Groupon
* LinkedIn
* Vine
* Chipotle
* Live Nation

Ember incorporates best practices and common idioms into the framework


## step 1: install ember
  run
  ```
  npm install -g ember-cli@2.14
  ```
once ember is installed
  run
  ```
  ember new ember-quickstart
  ```
  to create your app!

  this will create a directory called ember-quickstart which contains your ember app.

  cd into your new app's directory and run

  ```
  ember server
  ```
  to start your server.  You should see the following after a few seconds:
  ```
  Livereload server on http://localhost:49152
  Serving on http://localhost:4200/
  ```
  navigate to [http://localhost:4200] http://localhost:4200 and you should see the ember welcome screen.

  to create a route enter the following:
  ```
  ember generate route books
  ```
  this will generate a view template for books, a route, an entry in the router and a test route.

  here is an example of how to add some data to your model, open the newly created app/routes/books.js and enter your data

  ```
  import Ember from 'ember';

  export default Ember.Route.extend({
    model() {
    return ['The Great Gatsby', 'The Left Hand of Darkness', 'Foundation and Empire'];
    }
  });
  ```

  to view your newly created data navigate to the app/templates/books.hbs and enter the following:

  ```
  <h2>List of Books</h2>

  <ul>
    {{#each model as |book|}}
      <li>{{book}}</li>
    {{/each}}
  </ul>
  ```
  here we are using a simple each statement to loop through and display the list of books

## components
Ember alows the user to generate components that allows data to be shared between multiple views.

in order to generate a component enter the following into the terminal:

```
ember generate component books-list
```
then navigate to app/templates/components/books-list.hbs and enter the following:

```
<h2>{{title}}</h2>

<ul>
  {{#each books as |book|}}
    <li>{{book}}</li>
  {{/each}}
</ul>
```
Next delete ALL of the code in the books.hbs template and replace with the following:

```
{{books-list title="List of Books" books=model}}
```
navigate to http://localhost:4200/books and you should see the same info displayed but now the books-list can be reused across views.


## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](https://ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)
