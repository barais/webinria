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
  - From work at Xerox PARC in the late 70’s

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
1. FLEXIBLE! As big or small as you want it to be
  - Two line jQuery replacement to a MASSIVE enterprise app
2. POJOs make life so easy. No ‘observables’, wrappers etc. Uses dirty checking for 2-way binding.
  - Fully embraces the dynamic nature of JavaScript
3. The community and popularity
4. DI, services, factories, providers offer flexibility and familiarity to traditionally server side paradigms
5. Directives offer DSL-like extension to HTML for your domain specific use cases
6. Scopes, although tricky, offer extreme flexibility

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
