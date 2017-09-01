https://guides.emberjs.com/v2.14.0/getting-started/quick-start/

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
  navigate to [http://localhost:4200/] (http://localhost:4200) and you should see the ember welcome screen.

  to create a route enter the following:
  ```
  ember generate route scientists
  ```
  this will generate a view template for scientists, a route, an entry in the router and a test route.

  here is an example of how to add some data to your model, open the newly created app/routes/scientists.js and enter your data

  ```
  import Ember from 'ember';

  export default Ember.Route.extend({
    model() {
    return ['Marie Curie', 'Mae Jemison', 'Albert Hofmann'];
    }
  });
  ```

  to view your newly created data navigate to the app/templates/scientists.hbs and enter the following:

  ```
  <h2>List of Scientists</h2>

  <ul>
    {{#each model as |scientist|}}
      <li>{{scientist}}</li>
    {{/each}}
  </ul>
  ```
  here we are using a simple each statement to loop through and display the list of scientists

## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](https://ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)
