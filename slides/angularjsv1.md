##  Introduction to

<div align="center"><img src="resources/image_44.png" width="85%"></div>

----
## Early Web
- Web designed for documents
- Server creates pages / browser displays
- Data input sent to and processed by the server
- Updated pages created on the server and resent

----
## First Example - PHP

```html
<!doctype html>
<html>
<head>
</head>
<body>
  <form method="post" action="hello.php">
    <label>Name:</label>
    <input type="text" id="yourName”>
    <input type="submit" value="Say Hello" />
    <hr>
<?php
    echo "<h1>Hello ".$HTTP_POST_VARS["yourName"]."!</h1>";  
?>
  </form>
</body>
</html>
```

----
## Web Evolution - AJAX
- Interactive client-side web
  - Collect input from user
  - Update display
  - Communicate with server
- Client-side processing enabled by
  - JavaScript
  - DOM manipulation
  - HTTP server messaging

----
## First Example - jQuery
```html
<html>
<head>
  <script src="http://code.jquery.com/jquery-1.9.1.min.js"></script>
  <script type="text/javascript">                                         
   $(function() {
     $("#yourName").keyup(function () {
       $("#helloName").text("Hello " + this.value + "!");
     });
   });                                    
 </script>
</head>
<body>
  <div>
    <label>Name:</label>
    <input type="text" id="yourName">
    <hr>
    <h1 id="helloName"></h1>
  </div>
</body>
</html>
```

----
## jQuery
- Simplifies event binding and DOM manipulation
- Common API across multiple browsers
- Supports plug-in modules to extend functionality
- Requires writing JavaScript code to wire

----
## Today’s Web – Can we do better?

- Follow good programming practices
  - Separate: data / display / processing
  - Simplify connecting data to display
- Let us focus on the technologies of the web
  - HTML
  - CSS
  - JavaScript

----
## First Example - AngularJS
```html
<html ng-app>
<head>
  <script src="https://code.angularjs.org/1.5.3/angular.min.js"></script>
</head>
<body>
  <div>
    <label>Name:</label>
    <input type="text" ng-model="yourName">
    <hr>
    <h1>Hello {{yourName}}!</h1>
  </div>
</body>
</html>
```

----
## Imperative vs. Declarative
```html
<input type="text" id="yourName">
<h1 id="helloName"></h1>
<script type="text/javascript">
  $(function() {
    $("#yourName").keyup(function () {
      $("#helloName").text("Hello " + this.value + "!");
    });
  });
</script>
```
to AngularJS declarative relationships

```html
<input type="text" ng-model="yourName">
<h1>Hello {{yourName}}!</h1>
```

----
## Abstractions

- jQuery abstracts browser functionality
  - e.g. DOM traversal, event binding
- AngularJS abstracts relationships (and more)
 > AngularJS, and all web apps, are built on browser functionalities

----
## The DOM abstraction
- HTML is a declarative document language
- Browser translates HTML into a Document Object Model (DOM)
- DOM is the browser’s in-memory document representation
- JavaScript can manipulate the DOM

----
## AngularJS "*compiles*" HTML
- Browsers send a document (i.e. DOM) ready event
- AngularJS can intercede and rewrite the DOM
- The rewrite is driven by markup in the DOM

----
Model-View-Controller (MVC)

- Software architectural pattern
  - Separates display from data
  - Originated with Smalltalk programmers
  - From work at [Xerox PARC](http://heim.ifi.uio.no/~trygver/themes/mvc/mvc-index.html) in the late 70’s

- Models represent knowledge
- Views provide a (visual) representation of attached model data
- Controllers connect to and control views and models

----
## MVC and Variations

- Different variations of the pattern
- Model-View-ViewModel (MVVM)
- Model-View-Presenter (MVP)
- Variations differ on…
  - connectivity
  -  cardinality
  - directionality

----
## Model-View-Whatever
<div style="center"><font size="5">" <b>MVC vs MVVM vs MVP</b>. What a controversial topic that many developers can spend hours and hours debating and arguing about. For several years AngularJS was closer to <b>MVC</b> (or rather one of its client-side variants), but over time and thanks to many refactorings and api improvements, it's now closer to <b>MVVM – the $scope object could be considered the ViewModel</b> that is being decorated by a function that we call a Controller.<BR>
…<BR>
<b>I hereby declare AngularJS to be MVW framework - Model-View-Whatever.<b><BR>
…"<BR></font></div>
<font size="5">Igor Minar – Google AngularJS Development Team</font>

----
## Summary what is  AngularJS?
- An MVC framework for **efficiently** creating dynamic views in a web browser (using HTML and JavaScript)
- Some highlights/focuses:
  - Complete application framework
  - From *jQuery replacement* to a massive *enterprise* **Single Page Application (SPA)**
  - Fully dynamic MVVM with POJOs
  - Low level-DOM manipulation/markup invention with directives and templates
  - AJAX / REST API interaction
  - Code organization, dependency injection, testability
  - Comprehensive SPA and routing support

----
## Why should we care?
- It's open source
- Actively developed by Google
  - Google is paying devs to actively develop Angular
<div align="center"><img src="resources/image_58.jpg" width="25%"></div>
- Actively developed by open source community (on GitHub)
<div align="center"><img src="resources/image_59.png" width="25%"></div>

----
## Angular.js #1?

- Angular.js appears to be winning the JavaScript framework battle (and for good reason)
<div align="right"><img src="resources/image_62.jpg" width="15%"></div>
- Lets see some evidence…

----
## Why care? – GitHub Stats

 | Angular | Ember | Backbone | Knockout | Durandal
 -- | -- | -- | -- | -- | --
Stars | 54,449 | 17,438| 25,976 | 7,977 | 1,761
Watches | 4,477 | 1,093 | 1,627| 606 |  192
Forks  | 27,072 | 3,646| 5,641 | 1,371| 395
commit | 8,329 | 13,969 | 3,337 | 1,484 | 1,189
release | 185 | 232 | 30 | 38 | 6
contributors | 1,562  | 638| 292 | 62 | 70

----
## Why care? – Google trends
<div align="center"><img src="resources/Image2.png" width="100%"></div>

----

AngularJS vs jQuery

- jQuery is a library meant for is DOM manipulation, animations and an AJAX wrapper. NOT an application framework
- **Pros**
  - None. Angular has built in ‘basic’ jQuery.
  - If full-blown jQuery is added Angular will automatically use it. Generally full blown NOT needed.
- **Cons**
  - Horrible choice for creating dynamic UIs.
  - Verbose code, hard to maintain, not organized
  - Not MVVM or MVC

----
##AngularJS vs BackBoneJS

- Provides structure to web applications as well as model, view, templating, basic routing and RESTful interactions.

- **Pros**
  - Older and more mature, more people using it
- **Cons**
  - *Previous generation* web app framework
    - No MVVM w/o addons – use jQuery for DOM manip.
    - No DI, not as easily testable
    - Not a full-featured framework, meant to be ‘light’
    - Extremely verbose for what you get
  - Not actively developed

  ----
  ##AngularJS vs Knockout.js

- A library that provides MVVM data bindings using observables and dependency tracking
- **Pros**
  - Possibly more performant under some situations
- **Cons**
  - Complicated and error prone
      - Dependency tracking, computeds get confusing
        - “when complicated things break it's hard to figure out why”
      - No POJO. Have to create “types” and ko.observable()s
  - All it does is MVVM, not an app framework
     - Testability, code organization etc. all potential issues

----
##AngularJS vs Durandal.js

- Provides an app framework around Knockout
- **Pros**
  - Has a few features not baked into Angular (though readily available 3rd party from Angular community)
- **Cons**
  - Uses Knockout for data binding, suffers from same knockout issues
  - Lacking many Angular.js features
  - No one is using it
  - Is mostly a 1 man show (Rob Eisenberg)

----
## Why Angular can be good (2)
1. FLEXIBLE! As big or small as you want it to be<!-- .element: class="fragment" -->
  - Two line jQuery replacement to a MASSIVE enterprise app
2. POJOs make life so easy. No ‘observables’, wrappers etc. Uses dirty checking for 2-way binding.<!-- .element: class="fragment" -->
  - Fully embraces the dynamic nature of JavaScript
3. The community and popularity<!-- .element: class="fragment" -->
4. DI, services, factories, providers offer flexibility and familiarity to traditionally server side paradigms<!-- .element: class="fragment" -->
5. Directives offer DSL-like extension to HTML for your domain specific use cases<!-- .element: class="fragment" -->
6. Scopes, although tricky, offer extreme flexibility<!-- .element: class="fragment" -->

----
## Why Angular can be good (2)
1. Efficient

<div align="center"><img src="resources/image_81.png" width="60%"></div>

----
## Why I don't didn't like Angular

- Scopes are hard initially, but awesome
- Learning curve === eventual productivity

<div align="center"><img src="resources/image_82.png" width="50%"></div>


----
## Code time! A simple example

```html
<html>
<head>
  <script src="https://code.angularjs.org/1.5.3/angular.min.js"></script>
</head>
<body  ng-app="my-app">
  <div ng-controller="exempleCtrl">
    <label>Name:</label>
    <input type="text" ng-model="yourName">
    <hr>
    <h1>Hello {{yourName}}!</h1>
  </div>
</body>
</html>
```

----
## Code time! A simple example
```js
var app = angular.module("my-app", []);

app.controller("exempleCtrl", function($scope) {
    $scope.yourName = "World"
});
```

----
## Code time! A simple example
```js
var app = angular.module("my-app", []);
app.controller("exempleCtrl", function($scope) {
    $scope.yourName = "World";
    var observeYourName = function(){
      console.log('new value' + $scope.yourName);
    };
    $scope.$watch('yourName', observeYourName);
});
```

----
## Simple example

- ng-app attribute causes Angular to scan children for recognized tokens
  - Creates the “root scope” $rootScope
  - $rootScope ≈ a ViewModel
( Angular sees three “directives”
  - *({{yourName}}*
- Evaluated against the current $rootScope and updates the DOM on any change. "1 – way bound"
  - *ng-model="firstName"*
- An input to be 2-way bound against $scope.yourName
  - *ng-model="lastName"*
- An input to be 2-way bound against *$scope.yourName*

----
<div align="center"><img src="resources/test.svg" width="100%"></div>

----

## What is Scope?

-  Scope is an object that refers to the application model. It is an execution context for expressions. Scopes are arranged in hierarchical structure which mimic the DOM structure of the application. Scopes can watch expressions and propagate events. (from Angular website)

- **Key points**
  - Scope is like a ViewModel that allows communication between JavaScript code and Views
  - *{{yourName}}* is an expr executed against scope
  - Scope can be hierarchal with DOM nesting of directives
  - Watches can be used to watch for changes to scope ex:

```js
$scope.$watch("yourName", function(value) {
	//update the DOM with the new value
});
```

----
## What is a Directive?
- A reusable component for performing DOM interaction, templating and possibly two-way binding against $scope
  - The ONLY place JS to DOM interaction should occur
- Angular offers a huge amount of built in directives for common UI tasks, ex:
```html
<div ng-show="someBool">someBool is true!</div>
```
  - 2 way binding inputs, setting classes, foreach loops of elements, clicking etc.

----
  ## What is a Directive?

- You can write your own directives for domain specific purposes (a ‘DSL’ for HTML). Ex:

```html
<slideshow title="Shocked Cats">
<slide src="cat1.jpg"></slide>
<slide src="cat2.jpg"></slide>
…
</slideshow>
```
<p class="fragment current-visible"
style="position:absolute; left:650px; top:150px;">
<img src="resources/image_95.jpg" width="300"/></p>

----
## What is a Directive?

- Or simply invoke an existing jQuery plugin
```html
<datepicker ng-model="aDate"></datepicker>
```
- Or if you need <=IE8 support:

```html
<input type="text" datepicker="" ng-model="aDate"/>
```

----
## What is a Directive?

- HUGE amount of directives out there due to Angular's popularity. Rarely have to write your own other than domain specific directives
  - EX: AngularUI
  - Twitter bootstrap wrappers
  - Select2
  - Sorting
  - Input masking
  - Enhanced router
  - Etc…
  - Various wrappers for jQuery UI components (ex: datepicker)
  <p style="position:absolute; left:650px; top:250px;">
  <img src="resources/image_97.jpg" width="200px"/></p>


----
## Adding “message updates" with a Controller
<div align="center"><img src="resources/image_83.jpg" width="80%"></div>

----
## What is a Controller?

- A controller is really just a fancy name for a "scope container" that prototypically inherits from its parent scope container.
- A controller can interact with **$scope** (the 'view model') which the view can also interact with.
<div align="center"><img src="resources/Controller.svg" width="40%"></div>


----
## Directives and Scope
<div style="position:absolute; left:0px;  width:300px;font-size: 18pt;"  align="left">
- A controller is really a directive that is configured to prototypically inherit from its parent <BR>
- Directives can be configured for what type of scope they create and parent access they have <BR>
Use "AngularJS Batarang" plugin for Chrome to explore scopes
</p></div>

<p style="position:absolute; right:0px; top:50px;">
<img src="resources/rootScope.svg" width="500px"/></p>

----
## Services
- Software architectural components
- Services provide data and compute
- Exist across views
- Depend on other services
- AngularJS has 20+
- [*$http*](https://docs.angularjs.org/api/ng/service/$http) – service to communicate with servers
- [*$log*](https://docs.angularjs.org/api/ng/service/$log) – service to do pretty log messages


----
## Server Communication

- *$http* service
  - Input config object
  - Returns promise
  - Communication is asynchronous

```js
$http({method: ‘GET’, url: fetchUrl})
  .success(function(data, status) {
    // process the data here
  })
  .error(function(data, status) {
    // error handling
});
```

----
## Promises
- [Promises](https://docs.angularjs.org/api/ng/service/$q) represent result of an action
- Particularly used with asynchronous actions
- They are either resolved or rejected


----


## Dependency Injection (DI)
- DI is a software architectural pattern
- Separation of concerns
- Service creation independent from usage
- Good for
  - Modular code
  - Allows AngularJS to wire in correct order
  - Supports substitution (for patching and testing)

----
## DI and JavaScript Minification
- Services identified by parameter name
- Minification obfuscates the name
- Pass names as strings in array

```js
angular.module('GoaleryServices')
  .factory('StatusManager',
    [          'CloudLogin', '$q',
      function (cloudLogin,   $q) {
...
}]);
```

----
## Fixing the ugly dates and ordering with Filters
<div align="center"><img src="resources/image_83.jpg" width="80%"></div>

----
## What is a Filter?
- A function that transforms an input to an output
  - Reminds me a lot of LINQ extension method lambdas in .NET
  - Can be "piped" UNIX style
  - Can create own
  - Angular has many built in filters:
    - currency, date, filter, json, limitTo, lowercase, number, orderBy, uppercase
    <p style="position:absolute; right:0px; top:-50px;">
    <img src="resources/image_118.jpg" width="150px"/></p>

----
## Validation with ng-form
<div align="center"><img src="resources/image_83.jpg" width="80%"></div>

----
## What is ng-form?
- NOT a traditional HTML "form"
  - Requires a "name" and "ng-model" on each input you wish to validate
  - Angular will not push invalid values back into bound $scope
- Allows for validation of collections of controls
  - Applies CSS classes to elements based on their validity
  - Lots of built in validator directives that work with ng-form:
```html
required=""
ng-minlength="{number}"
ng-maxlength="{number}"
ng-pattern="{string}"
ng-change="{string}"
```

----
## What is ng-form?
- Angular UI has some extensions
- AngularAgility - FormExtensions makes it easier
- [demo](http://angularagility.herokuapp.com/#/formExtensions/formExtensions/basic)

----
## AngularJS is pure JavaScript

- Prototype-based scripting language
- Dynamic, weakly typed, first-class functions

- Great JavaScript book:
  - Crockford (2008) JavaScript: The Good Parts – O’Reilly

----
## Testing AngularJS Apps

- JavaScript doesn’t have a compiler
- Must execute code to test
- Testability was a fundamental objective of AngularJS
  - Miško Hevery (AngularJS creator)
  - Previously created JsTestDriver

----
## AngularJS supports testing

- [Unit testing](https://docs.angularjs.org/guide/unit-testing) support
    - JsTestDriver
    - Jasmine
- DI allows substituting mocks for hard to test code
  - Server communication
  - Logging
- Angular Scenario Runner – [E2E testing](https://docs.angularjs.org/guide/dev_guide.e2e-testing)
  - Simulates user interations

----
## Building Web Apps
- Single web page
  - Loads the base HTML and included sources once
  - App changes views dynamically
- Server is called upon when needed
- Prefer using asynchronous server calls
  - Data changes
  - Fetch more data

----
  ## Building Web Apps

- Declarative view specification
- HTML augmented with:
  - Directives, Markup, Filter, Form Controls
- Loaded either
  - with a simple single web page
  - dynamically into a [view](https://docs.angularjs.org/api/ng/directive/ngView) as partials

----
## URL Routing

- Define the mapping from URL to view
- Can also bind controller
- Define URL parameters

```js
$routeProvider.when('/Book/:bookId', {
    templateUrl: 'book.html',
    controller: BookCntl
  });
  $routeProvider.when('/Book/:bookId/ch/:chapterId', {
    templateUrl: 'chapter.html',
    controller: ChapterCntl
  });
```

----
## Deep Linking
- AngularJS navigation updates the browser address bar
- Uses the HTML5 history API – fallback to hash-bang (#!) URL
- Users can link to pages in you app
- Server must recognize the link pattern and serve the application
- https://github.com/angular-ui/ui-router/wiki/Quick-Reference

----
## Creating Directives
- [Directives](https://docs.angularjs.org/guide/directive) package reusable HTML
- Naming nuance: "myDir" becomes "my-dir"
- Conceptual compile and link phases
- Can specify: scope, binding, restrictions, etc
- Supports transclusion
   - In computer science, transclusion is the inclusion of part or all of an electronic document into one or more other documents by hypertext reference.
- Consider creating a custom DSL

----
## Modules
- Packaging of JavaScript code
- [Modules](https://docs.angularjs.org/guide/module) declare dependencies
- AngularJS instantiates in correct order
- Provides separation of namespaces

----
## Let us practice
- Let us use the yeoman generator
- Install `yo`, `grunt-cli`, `bower`, `generator-angular` and `generator-karma`:
```bash
npm install -g grunt-cli bower yo generator-karma generator-angular
```

If you are planning on using Sass, you will need to first install Ruby and Compass:
- Install Ruby by downloading from [here](http://rubyinstaller.org/downloads/) or use Homebrew
- Install the compass gem:
```bash
gem install compass
```

----
## Let us practice
- Make a new directory, and `cd` into it:
```bash
mkdir my-new-project && cd $_
```
- Run `yo angular`, optionally passing an app name:
```bash
yo angular [app-name]
```

Run `grunt` for building and `grunt serve` for preview

----
## Generators and sub
 * [angular](#app) (aka [angular:app](#app))
 * [angular:controller](#controller)
 * [angular:directive](#directive)
 * [angular:filter](#filter)
 * [angular:route](#route)
 * [angular:service](#service)
 * [angular:provider](#service)
 * [angular:factory](#service)
 * [angular:value](#service)
 * [angular:constant](#service)
 * [angular:decorator](#decorator)
 * [angular:view](#view)

----
### App
- Sets up a new AngularJS app, generating all the boilerplate you need to get started. The app generator also optionally installs Bootstrap and additional AngularJS modules, such as angular-resource (installed by default).

Example:
```bash
yo angular
```

----
### Route
- Generates a controller and view, and configures a route in `app/scripts/app.js` connecting them.
- Example:

```bash
yo angular:route myroute
```

- Produces `app/scripts/controllers/myroute.js`:

```javascript
angular.module('myMod').controller('MyrouteCtrl', function ($scope) {
  // ...
});
```

- Produces `app/views/myroute.html`:

```html
<p>This is the myroute view</p>
```

----
- **Explicitly provide route URI**
- Example:
```bash
yo angular:route myRoute --uri=my/route
```

- Produces controller and view as above and adds a route to `app/scripts/app.js` with URI `my/route`

----
### Controller
- Generates a controller in `app/scripts/controllers`.
- Example:
```bash
yo angular:controller user
```

- Produces `app/scripts/controllers/user.js`:
```javascript
angular.module('myMod').controller('UserCtrl', function ($scope) {
  // ...
});
```

----
### Directive
- Generates a directive in `app/scripts/directives`.
- Example:
```bash
yo angular:directive myDirective
```

- Produces `app/scripts/directives/myDirective.js`:
```javascript
angular.module('myMod').directive('myDirective', function () {
  return {
    template: '<div></div>',
    restrict: 'E',
    link: function postLink(scope, element, attrs) {
      element.text('this is the myDirective directive');
    }
  };
});
```


----
### Filter
- Generates a filter in `app/scripts/filters`.
- Example:

```bash
yo angular:filter myFilter
```

Produces `app/scripts/filters/myFilter.js`:
```javascript
angular.module('myMod').filter('myFilter', function () {
  return function (input) {
    return 'myFilter filter:' + input;
  };
});
```

----
### View
- Generates an HTML view file in `app/views`.
- Example:
```bash
yo angular:view user
```

- Produces `app/views/user.html`:
```html
<p>This is the user view</p>
```

----
### Service
- Generates an AngularJS service.
- Example:
```bash
yo angular:service myService
```

- Produces `app/scripts/services/myService.js`:
```javascript
angular.module('myMod').service('myService', function () {
  // ...
});
```

- You can also do `yo angular:factory`, `yo angular:provider`, `yo angular:value`, and `yo angular:constant` for other types of services.

----
### Decorator
- Generates an AngularJS service decorator.
- Example:
```bash
yo angular:decorator serviceName
```

- Produces `app/scripts/decorators/serviceNameDecorator.js`:
```javascript
angular.module('myMod').config(function ($provide) {
    $provide.decorator('serviceName', function ($delegate) {
      // ...
      return $delegate;
    });
  });
```

----
## Options
In general, these options can be applied to any generator, though they only affect generators that produce scripts.

----

### CoffeeScript and TypeScript
For generators that output scripts, the *--coffee* option will output CoffeeScript instead of JavaScript, and *--typescript* will output TypeScript instead of JavaScript.

- For example:
```bash
yo angular:controller user --coffee
```

- Produces `app/scripts/controller/user.coffee`:
```coffeescript
angular.module('myMod')
  .controller 'UserCtrl', ($scope) ->
```

----
- For example:
```bash
yo angular:controller user --typescript
```

- Produces *app/scripts/controller/user.ts*:

```ts
/// <reference path="../app.ts" />

'use strict';

module demoApp {
    export interface IUserScope extends ng.IScope {
        awesomeThings: any[];
    }

    export class UserCtrl {

        constructor (private $scope:IUserScope) {
	        $scope.awesomeThings = [
              'HTML5 Boilerplate',
              'AngularJS',
              'Karma'
            ];
        }
    }
}

angular.module('demoApp')
  .controller('UserCtrl', demoApp.UserCtrl);
```

----

### Minification Safe

**tl;dr**: You don't need to write annotated code as the build step will
handle it for you.

<blockquote style="font-size:18pt;"> By default, generators produce unannotated code. Without annotations, AngularJS's DI system will break when minified. Typically, these annotations that make minification safe are added automatically at build-time, after application files are concatenated, but before they are minified. The annotations are important because minified code will rename variables, making it impossible for AngularJS to infer module names based solely on function parameters.</blockquote>

<blockquote style="font-size:18pt;"> The recommended build process uses `ng-annotate`, a tool that automatically adds these annotations. However, if you'd rather not use it, you have to add these annotations manually yourself. Why would you do that though? If you find a bug
in the annotated code, please file an issue at [ng-annotate](https://github.com/olov/ng-annotate/issues).</blockquote>


----

### Add to Index
- By default, new scripts are added to the index.html file. However, this may not always be suitable. Some use cases:
 * Manually added to the file
 * Auto-added by a 3rd party plugin
 * Using this generator as a subgenerator
- To skip adding them to the index, pass in the skip-add argument:

```bash
yo angular:service serviceName --skip-add
```

----
## Bower Components

- The following packages are always installed by the [app](#app) generator:
  * angular
  * angular-mocks

----
  ## Bower Components
- The following additional modules are available as components on bower, and installable via `bower install`:
  * angular-animate
  * angular-aria
  * angular-cookies
  * angular-messages
  * angular-resource
  * angular-sanitize

<blockquote style="font-size:18pt;">All of these can be updated with `bower update` as new versions of AngularJS are released.</blockquote>


----

## Configuration
Yeoman generated projects can be further tweaked according to your needs by modifying project files appropriately.


----

### Output
- You can change the `app` directory by adding an `appPath` property to `bower.json`. For instance, if you wanted to easily integrate with Express.js, you could add the following:

```json
{
  "name": "yo-test",
  "version": "0.0.0",
  ...
  "appPath": "public"
}

```
- This will cause Yeoman-generated client-side files to be placed in `public`.



----
### Output
- Note that you can also achieve the same results by adding an `--appPath` option when starting generator:
```bash
yo angular [app-name] --appPath=public
```

----

## Testing

Running
```bash
grunt test
```
will run the unit tests with karma.
