##  Tools for JavaScript Development

### Unleash the Power of JavaScript Tooling

----

## Table of Contents

- JavaScript Editors
  - JetBrains WebStorm
  - Sublime Text 2/3
  - Atom
  - Visual Code Editor

- Project tools
  - Package Management: NPM/Yarn & Bower
  - Scaffolding: Yeoman
  - Task Automation: Grunt && Gulp


----

# JavaScript Editors

----
##   JetBrains WebStorm

- JavaScript IDE suitable for both client-side JavaScript and server (Node.js) development
  - Livereload
  - Build
  - Code highlighting/Intellisense for:
    - LESS/SASS/Stylus CSS preprocessors
    - CoffeeScript/TypeScript JavaScript preprocessors
    - AngularJS directives
    - Emmet Coding
  - Has only 30-days-long free trial

----

## Sublime Text 2/3

- Editor for scripting languages
  - JavaScript, PHP, Python, Ruby, etc…
  - Basic code highlighting with vanilla installation
    - Endless number of configurable plugins
  - Free product
    - Paid only if used commercially
  - With plugins support for:
    - LESS/SASS/Stylus
    - CoffeeScript/TypeScript

----
## Atom: A hackable text editor


- Cross-platform editing
- Built-in package manager
- Smart autocompletion
- File system browser
- Under the hood
    - Atom is a desktop application built with HTML, JavaScript, CSS, and Node.js integration. It runs on Electron, a framework for building cross platform apps using web technologies.
- Open source
  - support by Github


----
## Visual Code Editor

- Smart autocompletion with IntelliSense.
  - smart completions based on variable types, function definitions, and imported modules.
- Debugging support
- Git commands built-in
- Extensible and customizable
- great integration of TypeScript and Angular 2
- Open source
  - support by Microsoft


---
## Project Tools
### No matter the Editor

----
## Project Tools

- NPM, Yarn & Bower
  - Install Node.js packages or client libraries
- Grunt & Gulp
  - Tasks runner
  - Create different tasks for build/development/test cases
- Yeoman
  - Scaffolding of applications
  - One-line-of-code to create a project template with views/routes/modules/etc…

----
## Package Management

### NPM, Yarn & Bower

----
## Package Management: NPM

- Node.js Package Management (NPM)
- Package manager for Node.js modules
```bash
npm init #in CMD (Win) or Terminal (MAC/Linux)
```
- Initializes an empty Node.js project with package.json file

```bash
 npm init
//enter package details
name: "NPM demos"
version: 0.0.1
description: "Demos for the NPM package management"
entry point: main.js
test command: test
git repository: http://github.com/user/repository-name
keywords: npm, package management
author: doncho.minkov@telerik.com
license: BSD-2-Clause
```

----
## Package Management: NPM

<div align="left"> - Installing modules</div>

```bash
npm install package-name [--save][--save-dev][--save-optional]
# Installs a package to the Node.js project
```
<pre> *-S*, *--save*: Package will appear in your dependencies
in package.json
   *-D*, *--save-dev*: Package will appear in
   your devDependencies
   *-O*, *--save-optional*: Package will appear in
   your optionalDependencies.
</pre>
```bash
npm install express --save-dev
```
 Before running the project
```bash
npm install ## Installs all missing packages from package.json
```

----

## Package Management: Bower

- Bower is a package management tool for installing client-side JavaScript libraries
  - Like jQuery, KendoUI, AngularJS, etc…
  - It is a Node.js package and should be installed first
```bash
npm install –g bower
bower init # in CMD (Win) or Terminal (Mac/Linux)
```
- Asks for pretty much the same details as *$ npm init*
- Creates bower.json file to manage libraries

----

## Package Management: Bower

- Searching for libraries
```bash
bower search kendo
```
<div align="center"><img src="resources/image_39.png" width="40%"></div>
- Installing libraries
```bash
bower install kendo-ui
```
<div align="center"><img src="resources/image_40.png" width="40%"></div>


----

## Grunt & Gulp
### Tasks Runner

----
## Grunt

- Grunt is a Node.js task runner
  - It can runs different tasks, based on configuration
  - Tasks can be:
    - Concat and minify JavaScript/CSS files
    - Compile SASS/LESS/Stylus
    - Run jshint, csshint
    - Run Unit Tests
    - Deploy to Git, Cloud, etc…
    - And many many more

----
## Grunt
- Why use a task runner?
  - Task runners gives us automation, even for different profiles:


  ** DEVELOPMENT **	| ** TEST** | ** BUILD **
  -- | -- | --
  jshint | jshint | jshint
  stylus | stylus | stylus
  csshint | csshint | csshint
  connect | mocha | concat
  watch | | uglify
| | copy
| | usemin

----
## Configuring Grunt

- To configure grunt, create a Gruntfile.js file in the root directory of your application
  - It is plain-old Node.js
  - Grunt is configured programmatically
  - Create an module that exports a single function with one parameter – the grunt object
```js
  module.exports = function (grunt) {
    //configure grunt
  };
```

----
## Configuring Grunt (2)

- All the configuration is done inside the module
- First execute the *grunt.initConfig()* method and pass it the configuration
```js
module.exports = function (grunt) {
  grunt.initConfig({
    ...
  });
};
```

----
## Configuring Grunt Plugins

- To use a plugin in grunt:
  - Install the plugin
```bash
npm install grunt-contrib-jshint --save-dev
```
  - Load the plugin
```js
//inside the grunt module
grunt.loadNpmTasks('grunt-contrib-jshint');
```
  - Configure the plugin
```js
//inside the grunt.initConfig()
grunt.initConfig({
  jshint: {
    app: ['Gruntfile.js',
      'path/to/scripts/**/*.js']
  }
});
```

----
## Grunt Plugins

----
## Grunt Plugins: Build
- *jshint (grunt-contrib-jshint )*
  - Runs jshint for specified files
- *csslint(grunt-contrib-csshint)*
  - Runs csslint for specified files
- *stylus (grunt-contrib-stylus)*
  - Compiles STYL files into CSS files
- *uglify (grunt-contrib-uglify)*
  - Minifies configured JavaScript files
- *concat (grunt-contrib-concat)*
  - Concats configured JavaScript files

----
## Grunt Plugins: Development
- *connect (grunt-contrib-connect)*
  - Stars a Web server on a given port and host
- *watch (grunt-contrib-watch)*
  - Watches for changes to configured files
  - Can run other tasks on file changed

----
## Gulp: The streaming build system


> Streams come to us from the earliest days of unix and have proven themselves over the decades as a dependable way to compose large systems out of small components that do one thing well.

> You can then plug the output of one stream to the input of another and use libraries that operate abstractly on streams to institute higher-level flow control.

----
## Why streams?

### Picture a build system in your head.
- It should take in files, modify them, and output the new ones



----
## You pictured this
<div align="center"><img src="resources/anim/B0B77QN.png" width="80%"></div>


----
## You didn't pictured this
<div align="center"><img src="resources/anim/oeCGJUS.png" width="80%"></div>

----
## What is wrong with Grunt
- Plugins do multiple things
  - Want a banner? Use the javascript minifier
  - Plugins do things that don't need to be plugins
  - Need to run your tests? Use a plugin
- Grunt config format is a mess that tries to do everything
- Not idiomatic with "the node way"
- Headache of temp files/folders due to bad flow control

> Your build system should empower not impede

> It should only manipulate files - let other libraries handle the rest.

----
## Sample Gruntfile

```js
module.exports = function(grunt) {

  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    concat: {
      options: {
        separator: ';'
      },
      dist: {
        src: ['src/**/*.js'],
        dest: 'dist/<%= pkg.name %>.js'
      }
    },
    uglify: {
      options: {
        banner: '/*! <%= pkg.name %> <%= grunt.template.today("dd-mm-yyyy") %> */\n'
      },
      dist: {
        files: {
          'dist/<%= pkg.name %>.min.js': ['<%= concat.dist.dest %>']
        }
      }
    },
    qunit: {
      files: ['test/**/*.html']
    },
    jshint: {
      files: ['gruntfile.js', 'src/**/*.js', 'test/**/*.js'],
      options: {
        // options here to override JSHint defaults
        globals: {
          jQuery: true,
          console: true,
          module: true,
          document: true
        }
      }
    },
    watch: {
      files: ['<%= jshint.files %>'],
      tasks: ['jshint', 'qunit']
    }
  });

  grunt.loadNpmTasks('grunt-contrib-uglify');
  grunt.loadNpmTasks('grunt-contrib-jshint');
  grunt.loadNpmTasks('grunt-contrib-qunit');
  grunt.loadNpmTasks('grunt-contrib-watch');
  grunt.loadNpmTasks('grunt-contrib-concat');

  grunt.registerTask('test', ['jshint', 'qunit']);

  grunt.registerTask('default', ['jshint', 'qunit', 'concat', 'uglify']);

};
```
<pre>
1. Runs tests
2. Lints code
3. Concats javascript
4. Minifies it
5. Runs again if files are changed
</pre>

----

## What's the difference?

- With Gulp your build file is code, not config
- You use standard libraries to do things
- Plugins are simple and do one thing - most are a ~20 line function
- Tasks are executed with maximum concurrency
- I/O works the way you picture it

----


> Gulp does nothing but provide some streams and a basic task system
> Gulp has only 5 functions you need to learn

----


```js
gulp.task(name, fn)
```

- It registers the function with a name.
- You can optionally specify some dependencies if other tasks need to run first.

----


```js
gulp.run(tasks...)
```

- Runs all tasks with maximum concurrency
----


```js
gulp.watch(glob, fn)
```
- Runs a function when a file that matches the glob changes
- Included in core for simplicity

----


```js
gulp.src(glob)
```
- This returns a readable stream.
- Takes a file system glob (like grunt) and starts emitting files that match.
- This is piped to other streams

----


```js
gulp.dest(folder)
```
- This returns a writable stream
- File objects piped to this are saved to the file system

----
## Yeoman
### Application Scaffolding

----
## Yeoman
- Yeoman is a Node.js package for application scaffolding
  - Uses bower & NPM to install the js package
  - Has lots of generators for many types of applications:
    - MEAN, AngularJS, Kendo-UI, WebApp, WordPress, Backbone, Express, etc…
    - Each generators install both needed Node.js packages and client-side JavaScript libraries
    - Generated Gruntfile.js for build/test/serve

----
## Yeoman
<pre>Install Yeoman:</pre>
```bash
npm install –g yo
```
<pre>Install Yeoman generator:</pre>
```bash
npm install –g generator-jhipster
```
<pre>Scaffold Express application:</pre>
```bash
cd path/to/app/directory
yo jhipster
```
<pre>Generates:</pre>
<div align="center"><img src="resources/image_41.jpg" width="25%"></div>
