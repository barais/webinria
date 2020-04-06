# React
### A library for creating user interfaces.

<div align="center"><img src="resources/react/react.svg" width="30%"></div>

----
## What is React.js

- React is a JavaScript library created by a collaboration of Facebook and Instagram
- It’s not MVC, only the "V" in "MVC"
- Big Companies use React
  - Facebook, Instagram, Yahoo!, Airbnb, Sony, Netflix

----
## Why was React.js made?

- React isn’t an MVC framework
- React does not use templates
- React updates are dead simple (Reactive pattern)
- HTML is just the beginning

----
## How is React.js used?
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.6.1/react.js"> </script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.6.1/react-dom.js"> </script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.38/browser.min.js"> </script>
<script src="app.js" type="text/babel"> </script>

<div id="root"></div>

  ```
  Root DOM node


```js
const element = <h1>Hello, world</h1>;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```
Render React element into root DOM node


----

## How is React.js used?
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.6.1/react.js"> </script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.6.1/react-dom.js"> </script>

<div id="root"></div>

  ```
  Root DOM node


```js
const element = React.createElement('h1', null, 'Hello react');
ReactDOM.render(
  element,
  document.getElementById('root')
);
```
Render React element into root DOM node


----
## Update the Rendered Element

```js
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  ReactDOM.render(
    element,
    document.getElementById('root')
  );
}
setInterval(tick, 1000);
```

----
## How the technology works

- Elements, Component, and Properties
- Component Life Cycle
- JSX
- States
- Virtual DOM
- One Way Data Flow

----
## Rule 1: Build components, not templates.

----
## We all like separation of concerns, right?

----
## Separation of concerns:

> Reduce **coupling**, increase **cohesion**.

----
## Coupling is:

> The degree to which each program module relies on each of the other modules.

[wikipedia (Coupling)](http://en.wikipedia.org/wiki/Coupling_(computer_science))

----
## Cohesion is:
> "The degree to which elements of a module belong together."
[wikipedia (Cohesion)](http://en.wikipedia.org/wiki/Cohesion_(computer_science))

----
## Templates encourage a poor separation of concerns.

 So are Angular-style directives.

----
## *"View model"* tightly couples template to display logic.

```json
[{"price": "7.99", "product": "Back scratcher", "tableRowColor": "rgba(0, 0, 0, 0.5)"}]
```

----
## Display logic and markup are inevitably tightly coupled.

 How do you find DOM nodes?

----
## Display logic and markup are highly cohesive.

 They both show the UI.

----

## Templates separate technologies, not concerns.
 And they do it by being deliberately underpowered.

----
## Symptoms that your front-end technology is underpowered:

 Reliance on primitive abstractions (like {{> }} and {{#each }}).

----
## Symptoms that your front-end technology is underpowered:

Inventing lots of new concepts (that already exist in JavaScript).

----

## From the Angular directives docs:

> However isolated scope creates a new problem: if a transcluded DOM is a child of the widget isolated scope then it will not be able to bind to anything. For this reason the transcluded scope is a child of the original scope, before the widget created an isolated scope for its local variables. This makes the transcluded and widget isolated scope siblings.

----

## The framework cannot know how to separate your concerns for you.

It should only provide **powerful**, **expressive tools** for the user to do it correctly.

----

## This tool is a React component.

A **highly cohesive** building block for UIs **loosely coupled** with other components.

----

## As an architect, use components to separate your concerns.

With the full power of JavaScript, not a crippled templating language.

----

## Components are **reusable**.

----

## Components are **composable**.

----

## Components are **unit testable**.

They are, after all, units.

----

## What about spaghetti code?

----

## Just don’t write spaghetti code.
Keep your components small.

----

## Just don’t write spaghetti code.
Only put *display logic* in your components.

----

## Just don’t write spaghetti code.

> With great power comes great responsibility – Uncle Ben in Spiderman

----

## What about **working with designers**?

----

## JSX is an *optional* preprocessor to let you use HTML-like syntax.

```js
<a href=“http://olivier.barais.fr”>
    my personal web site
</a>
```

----

## JSX is an *optional* preprocessor to let you use HTML-like syntax.

```js
React.DOM.a(
  {href: 'http://olivier.barais.fr'},
  'my personal web site'
)
```

----

## With JSX, it’s easy for designers to contribute code.

----

## The accessibility of templates and the power of JavaScript.

----
# Rule 2. Re-render the whole app on every update

The **key design decision** that makes React awesome.

----

## Building UIs is hard because there is so much state.
Lots of UI elements · Design iteration · Crazy environments · Mutable DOM · User input · etc etc

----

## Data changing over time is the root of all evil.

----

> “Our intellectual powers are rather geared to master static relations and our powers to visualize processes evolving in time are relatively poorly developed. For that reason we should do (as wise programmers aware of our limitations) our utmost to shorten the conceptual gap between the static program and the dynamic process, to make the correspondence between the program (spread out in text space) and the process (spread out in time) as trivial as possible” – Dijkstra


----

## In the 90s it was easier.

Just refresh the page when the data changes.


----

## Design decision: When the data changes, **React re-renders the entire component**.

----

## That is, ** React components are basically just idempotent functions.**

They describe your UI at any point in time, just like a server-rendered app.

----
## Re-rendering on every change makes things simple.

- Every place data is displayed is guaranteed to be up-to-date.
- No magical data binding.
- No model dirty checking.
- No more explicit DOM operations – ** everything is declarative**

----
## "Re-render on every change? That seems expensive."

“And doesn't it mess up form fields and scroll position?”

----

# Rule 3. Virtual DOM

Makes re-rendering on every change fast.

----
### You can’t just throw out the DOM and rebuild it on each update.
It’s too slow and you’ll lose form state and scroll position.

----

## So React built a **virtual DOM** (and events system).
Optimized for performance and memory footprint

----
<div align="center"><img src="resources/react/img2.png" width="100%"></div>


----
## On every update...
- React builds a new virtual DOM subtree
- ... diffs it with the old one
- ... computes the minimal set of DOM mutations and puts them in a queue
- ... and batch executes all updates

----
<div align="center"><img src="resources/react/img3.png" width="100%"></div>



----
### It’s **fast**!
Because the DOM is slow!

----
## The virtual DOM lets us do fun things.
- **Testability** for free
- **SVG**, **VML** and **canvas** support
- Running the whole app in a Web Worker

----

## Other concepts


----
<div align="center"><img src="resources/react/img1.png" width="100%"></div>

----
## Props

```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Olivier" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```

----

### State

```js
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }
  componentDidMount() {
    this.timerID = setInterval(() => this.tick(),1000);
  }
  componentWillUnmount() { clearInterval(this.timerID);}
  tick() {
    this.setState({ date: new Date()});
  }
  render() {
    return
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
  }
}
ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);

```

----

## Component Lifecycle
- Mounting
- Updating
- Unmounting

----
## Mounting
1. constructor()
2. componentWillMount()
3. render()
4. componentDidMount()

----

## Updating
1. componentWillReceiveProps()
2. shouldComponentUpdate()
3. componentWillUpdate()
4. render()
5. componentDidUpdate()

----

## Unmounting
1. componentWillUnmount()

----

# Rule 4: a flow is unidirectional.

All data flows down the component hierarchy

----
## Communication between Components

- [props and context](https://www.pluralsight.com/guides/react-communicating-between-components)

[8 no-Flux strategies for React component communication](http://andrewhfarmer.com/component-communication/)

----
## Communication between Components

- Use Flux or Redux

----

## And it works with Typescript

- demo

```bash
npx create-react-app my-app --template typescript
cd my-app
npm start
```

----


## Conclusion on React
- Components, not templates.
- Three main concepts:
 - Components
 - Props
 - State
- Re-render, don’t mutate.
- Virtual DOM is **simple** and **fast**

- https://facebook.github.io/react/
