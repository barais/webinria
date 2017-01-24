##  TypeScript

----

## What is TypeScript?

- Free and open source, strongly supported by Microsoft
- Based on ecmascript 4 + ecmascript 6
- Created by the father of C# Anders Hejlsberg
- A superset of JavaScript
- To answer why we need JavaScript+, we need to understand what's wrong with vanilla JavaScript

----
## What is the problem ?

- Why do people hate working in JavaScript?
<div align="center"><img src="resources/image_42.jpg" width="150%"></div>
> Using state of the art software engineering practices ;)

----
## What is the problem ?

- JS is designed for small things
- We now use to do big things
- But JavaScript is not suited for building large applications
> Your JavaScript code gets complex; it becomes extremely unwieldy

----
## Let's look at TypeScript
- To get started with TypeScript, grab it from http://typescriptlang.org 
- Let's look at TypeScript, first the core concept…

----
## TypeScript - first glance - optional strong type checking

```ts
// jsfunction
f(x, y) {   return x * y;}
// tsfunction
f(x : number, y : number) : number {    return x * y;}
// Type information is enforced in design and
// compile time, but removed at runtime
```

----
## TypeScript features
- Static Type Checking
- Modules and Export
- Interface and Class for traditional Object Oriented Programming

- Works with all your existing JavaScript libraries
- Low learning overhead compared to similar JavaScript systems (CoffeeScript or Dart)

- Amazing Visual Studio, visual code studio, eclipse or IntelliJ tooling
- Outstanding team and refactoring scenarios

----
## Summary - why TypeScript ? (Expected Benefits)(1)
- Have to learn one more thing - there is a learning curve, very easy if you already know JavaScript, or if you know C# or Java very well.
- You still have to learn JavaScript - Understanding how TypeScript converts to JavaScript will teach you better JavaScript
- Some definition files don't exist or incomplete, but I think this will vanish very quickly.  These aren't hard to write if you really need something.

----
## Summary - why TypeScript ? (Expected Benefits)(2)
- Modules and classes enable large projects and code reuse
- Compile-time checking prevents errors
- Definition files for common JavaScript libraries makes them very easy to work with, and provides strong type checking
- Source map debugging makes debug easy

----
## Initial conclusion - if I have to make a decision for you…
- If you see yourself using more JavaScript.  You have to look at TypeScript.
- If you and your team has to work on JavaScript together, you have to look at TypeScript.
- Once you've done the initial hard work and converted a project.  You can't stand going back.
