
<div align="center"><img src="resources/angular2/AngularJS_logo.svg_-650x4011.png" width="70%"></div>

### A complete rewrite

----

## Why complete rewrite?

- JavaScript is more matured now
- Typescript is more mature now
- Browsers are more matured now
- Performance improvements
- Saying bye to some of old friends (scope, modules, DDO, controllers, jqLite)
- And several other reasons…

----
## Angularjs

- Open source
- Maintained by google and community
- Frontend framework
- Adjusts and adapts traditional HTML in order to present dynamic content through the two way data biding which allows instantaneous synchronization of views and models.

----
## Angularjs 2

- Release in September 2016
- Using TypeScript
- Many modern browsers support it (Even IE9)

----
## Typescript

- TypeScript is a typed superset of JavaScript that compiles to plain JavaScript
- Optional tipization and object oriented
- Supports ECMAScript 2015 features like async functions and decorators
- October 2012 (v0.8) Microsoft-a

----
## Typescript

```ts
class Student {
    fullName: string;
    constructor(public firstName, public middleInitial, public lastName) {
        this.fullName = firstName + " " + middleInitial + " " + lastName;
    }
}

interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person : Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

var user = new Student("Jane", "M.", "User");

document.body.innerHTML = greeter(user);
```

```html
<html>
    <head><title>TypeScript Greeter</title></head>
    <body>
        <script src="greeter.js"></script>
    </body>
</html>
```

----

## Typescript

- Additional functionalities
  - Modules, classes, interfaces, “arrow” syntaks, namespaces, enumerated types
- Weakly or dynamically typed (:any)
- Strongly typed (:string, :number, :Class)

----
## Angular 2 Core: Change Detection

- Unidirectional tree based change detection
- Unidirectional flow is a win for performance
- Change detection works with:
  - Plain JS Objects
  - Immutable Objects
  - Observable objects

----
## Big picture

<div align="center"><img src="resources/angular2/img1.png" width="100%"></div>

----
 ## Angularjs 2
- **Modules**
  - Contains parts of the application which we export
- **Components**
  - Application logic which controls parts of the user interface
- **Templates**
  - Renders the component on the page
- **Metadata**
  -- Information about the angular application parts

----
## Modules

app/app.component.ts:

```ts
export class AppComponent { }
```

app/boot.ts:

```ts
import {AppComponent} from './app.component';
```

> equivalent to decide which classes can be imported from a jar (Public Private for a module)

<p class="current-visible"
style="position:absolute; left:670px; top:130px;">
<img src="resources/angular2/img2.png" width="100%"></p>

----
## Library modules

```ts
import {Component} from 'angular2/core';
```
- Angular apps are composed of modules.
- Modules export things — classes, function, values — that other modules import.
- We prefer to write our application as a collection of modules, each module exporting one thing.

<p class="current-visible"
style="position:absolute; left:300px; top:400px;">
<img src="resources/angular2/img3.png" width="100%"></p>


----
## Component
```ts
export class HeroListComponent implements OnInit {
  constructor(private _service: HeroService){ }
  heroes: Hero[];
  selectedHero: Hero;
  ngOnInit(){
    this.heroes = this._service.getHeroes();
  }
  selectHero(hero: Hero) { this.selectedHero = hero; }
}
```
app/hero-list.component.ts

<p class="current-visible"
style="position:absolute; left:650px; top:-70px;">
<img src="resources/angular2/img4.png" width="100%"></p>


----

## Template
```html
<h2>Hero List</h2>
 
<p><i>Pick a hero from the list</i></p>
<div *ngFor="#hero of heroes" (click)="selectHero(hero)">
  {{hero.name}}
</div>
 
<hero-detail *ngIf="selectedHero" [hero]="selectedHero">
</hero-detail>
```
app/hero-list.component.html
 
<p class="current-visible"
style="position:absolute; left:650px; top:-70px;">
<img src="resources/angular2/img5.png" width="100%"></p>


----
## Metadata

```ts
@Component({
  selector:    'hero-list',
  templateUrl: 'app/hero-list.component.html',
  directives:  [HeroDetailComponent],
  providers:   [HeroService]
})
export class HeroesComponent { ... }
```

- **selector** : a css selector that tells Angular to create and insert an instance of this component where it finds a <hero-list> tag in parent HTML.
```html
<hero-list></hero-list>```
  - Angular inserts an instance of the HeroListComponent view between tags.
- **templateUrl**: the address of this component's template

<p class="current-visible"
style="position:absolute; left:750px; top:-30px;">
<img src="resources/angular2/img6.png" width="100%"></p>

----
## Metadata

```ts
@Component({
  selector:    'hero-list',
  templateUrl: 'app/hero-list.component.html',
  directives:  [HeroDetailComponent],
  providers:   [HeroService]
})
export class HeroesComponent { ... }
```

- **directives**: an array of the Components or Directives this template requires
- **providers**: an array of dependency injection providers for services that the component requires

<p class="current-visible"
style="position:absolute; left:750px; top:-30px;">
<img src="resources/angular2/img6.png" width="100%"></p>

----
## Data binding

```html
<div>{{hero.name}}</div>
<hero-detail [hero]="selectedHero”></hero-detail>
<div (click)="selectHero(hero)></div>
```
app/hero-list.component.ts

<p class="current-visible"
style="position:absolute; left:0px; top:250px;">
<img src="resources/angular2/img7.png" width="80%"></p>

<p class="current-visible"
style="position:absolute; left:400px; top:250px;">
<img src="resources/angular2/img8.png" width="80%"></p>


----
## Component interaction

<div align="center"><img src="resources/angular2/img11.png" width="100%"></div>

----
## Component interaction

<div align="center"><img src="resources/angular2/img12.png" width="100%"></div>


----
## Component interaction


> “Inputs”, as you might guess from the hierarchy discussion above, specifies which properties you can set on a component whereas “outputs” identifies the events a component can fire to send information up the hierarchy to its parent.



----
## Example: component

```ts
import {Component} from 'angular2/core';
@Component({
    selector: 'my-app',
    template: '
      <h1>{{title}}</h1>
      <h2>My favorite hero is: {{myHero}}</h2>
    '
})
export class AppComponent {
    title = 'Tour of Heroes';
    myHero = 'Windstorm';
}
```
app.ts
```html
<body>
    <my-app>Loading...</my-app>
</body>
```
index.html

----
## Example: show the list of heroes
```ts
export class AppComponent {
    title = 'Tour of Heroes';
    heroes = ['Windstorm', 'Bombasto', 'Magneta', 'Tornado'];
    myHero = this.heroes[0];
}
```
Component

```html
  <h1>{{title}}</h1>
  <h2>My favorite hero is: {{myHero.name}}</h2>
  <p>Heroes:</p>
  <ul>
    <li *ngFor="#hero of heroes">
      {{ hero.name }}
      </li>
  </ul>
  <p *ngIf="heroes.length > 3">There are many heroes!</p>
```
template


----
## Example: create class for data and fill it


```ts
export class Hero {
    constructor(
        public id:number,
        public name:string) { }
  }
```
hero.ts

```ts
export class AppComponent {
    title = 'Tour of Heroes';
    heroes = [
        new Hero(1, 'Windstorm'),  new Hero(13, 'Bombasto'),
        new Hero(15, 'Magneta'),  new Hero(20, 'Tornado')
    ];
    myHero = this.heroes[0];
  }
```
app.component.ts:

----
## Example: work with the events

```ts
@Component({
    selector: 'click-me',
    template: `
        <button (click)="onClickMe()">Click me!</button>
        {{clickMessage}}`
})
export class ClickMeComponent {
    clickMessage = '';
    onClickMe() {
        this.clickMessage ='You are my hero!';
    }
}
```

----
## Example: adding hero form

```ts
@Component({
    selector: 'little-tour',
    template: `
      <input #newHero
          (keyup.enter)="addHero(newHero.value)"
          (blur)="addHero(newHero.value); newHero.value='' ">
      <button (click)=addHero(newHero.value)>Add</button>
      <ul><li *ngFor="#hero of heroes">{{hero}}</li></ul>
    `
})
export class LittleTourComponent {
    heroes=['Windstorm', 'Bombasto', 'Magneta', 'Tornado'];
    addHero(newHero:string) {
        if (newHero) {
            this.heroes.push(newHero);
        }
    }
}
```

----

## Example: execute

```ts
import {bootstrap}    from 'angular2/platform/browser'
import {AppComponent} from './app.component'
bootstrap(AppComponent);
```
boot.ts


```json
	name, version
	dependencies (SystemJS is used as module system)
	devDependencies
```
package.json

```json
	TypeScript configuration
```
tsconfig.json

```sh
npm start
```

----

## Binding in templates

Data Direction | Syntax | Binding Type |
-- | -- | --
One way from data <BR> source to view target | <p  style = "font-size:25px">{{expression}} <BR> [target] = "expression"  <BR> bind-target = "expr" </p> | <p  style = "font-size:25px"> Interpolation <BR> Property <BR> Attribute <BR> Class <BR> Style</p>
One way from view <BR> target to data source | <p  style = "font-size:25px">(target) = "expression"  <BR> on-target = "expr" </p>| <p  style = "font-size:25px"> Event</p>
Two way | <p  style = "font-size:25px">[(target)] = "expr" <BR> bindon-target = "expr"  </p>| <p  style = "font-size:25px">Two-way</p>


----

## Binding targets

Binding Type | Target | Examples
---------------: | --- | --
Property | <p  style = "font-size:25px"> Element Property <BR> Component Property <BR> Directive property</p> | <p  style = "font-size:20px"> ```<img [src] = "heroImageUrl">```</p> <p  style = "font-size:20px"> ```<hero-detail [hero]="currentHero"></hero-detail>```</p> <p  style = "font-size:20px"> ``` <div [ngClass] = "{selected: isSelected}"></div>``` </p>
Event | <p  style = "font-size:25px"> Element Event <BR> Component Event <BR> Directive Event</p> |  <p  style = "font-size:20px"> ```<button (click) = "onSave()">Save</button>```</p> <p  style = "font-size:20px"> ```<hero-detail (deleted)="onHeroDeleted()"> </hero-detail>```</p> <p  style = "font-size:20px"> ```<div myClick(myClick)="clicked=$event">click me</div>```</p>

----

## Binding targets

Binding Type | Target | Examples
---------------: | --- | --
Two-way |  <p  style = "font-size:25px"> Directive <BR> Event Property </p>| <p  style = "font-size:20px"> ```<input [(ngModel)]="heroName">```</p>
Attribute | <p  style = "font-size:25px"> Attribute (the exception)</p> | <p  style = "font-size:20px"> ```<button [attr.aria-label]="help"> help </button>```</p>
Class | <p  style = "font-size:25px">class Property</p> | <p  style = "font-size:20px"> ```<div [class.special]="isSpecial"> Special </div>```</p>
Style | <p  style = "font-size:25px">style Property</p> | <p  style = "font-size:20px"> ```<button [style.color] = "isSpecial ? 'red' : 'green'">```</p>

----
## Dependency Injection

```ts
constructor(private _service: HeroService) { ... }
```
But how Injector get to know about service?

2 ways:

```ts
bootstrap(AppComponent, [HeroService, Logger]);
```
app/boot.ts

```ts
  @Component({
     providers:   [HeroService]
  })
  export class HeroesComponent { ... }
  ```
  app/hero-list.component.ts
<p style = "font-size:25px">(we get a new instance of the service with each new instance of that component)</p>
<p class="current-visible"
style="position:absolute; left:700px; top:50px;">
<img src="resources/angular2/img9.png" width="70%"></p>

----
## Example: define mock HeroService
```ts
import {HEROES} from './mock-heroes';
import {Injectable} from 'angular2/core';

@Injectable()
export class HeroService {
    getHeroes() {
        return HEROES;
    }
}
```
hero.service.ts:

```ts
import {Hero} from './hero';
export var HEROES: Hero[] = [
    {"id": 11, "name": "Mr. Nice"},
    {"id": 12, "name": "Narco"}
]
```
mock-heroes.ts

----
### Example: define HeroService with promises

```ts
import {Injectable} from 'angular2/core';
import {Hero} from './hero';
import {HEROES} from './mock-heroes';

@Injectable()
export class HeroService {
    getHeroes() {
        return Promise.resolve(HEROES);
    }
    // See the "Take it slow" appendix
    getHeroesSlowly() {
        return new Promise<Hero[]>(resolve =>
            setTimeout(()=>resolve(HEROES), 2000) // 2 seconds
        );
    }
}
```

----
### Example: use HeroService in component

```ts
import {Component, OnInit} from 'angular2/core';
import {HeroService} from './hero.service';
@Component({
    selector: 'my-app',
    template: `…`,
    providers: [HeroService]
})
export class AppComponent implements OnInit {
    heroes:Hero[];
    constructor(private _heroService:HeroService) { }
    getHeroes() {
        this._heroService.getHeroes()
		.then(heroes => this.heroes = heroes);
    }
    ngOnInit() {    this.getHeroes();    }
}
```

----
## Service
```ts
export class HeroService {
    constructor(private _backend:BackendService,
                		private _logger:Logger) {}
    private _heroes:Hero[] = [];

    getHeroes() {
        this._backend.getAll(Hero).then((heroes:Hero[]) => {
            this._logger.log(`Fetched ${heroes.length} heroes.`);
            this._heroes.push(...heroes); // fill cache

        });
        return this._heroes;
    }
}
```
app/hero.service.ts

----
## Forms

```html
<div class="form-group">
   <label for="power">Hero Power</label>
   <select class="form-control" required>
     <option *ngFor="#p of powers" [value]="p">{{p}}</option>
   </select>
</div>
```

NgControl
```html
<input type="text" class="form-control"
  required   
  [(ngModel)]="model.name"   
  ngControl="name" >
```

----
## Form validation

State | Class if true | Class if false
-- | -- | --
Control has been visited | ng-touched | ng-untouched
Control's value has changed | ng-dirty | ng-pristine
Control's value is valid | ng-valid | ng-invalid

```css
.ng-valid[required] {
   border-left: 5px solid #42A948; /* green */
}
.ng-invalid {
   border-left: 5px solid #a94442; /* red */
}
```

----
## Show validation messages

```html
<input type="text" class="form-control" required
  [(ngModel)]="model.name"
    ngControl="name"  #name="ngForm" >
<div [hidden]="name.valid" class="alert alert-danger">
  Name is required
</div>
```

----

## Routing
```ts
@Component({...})
@RouteConfig([
{   path: '/crisis-center',
    name: 'CrisisCenter',
    component: CrisisListComponent },
{   path: '/heroes',
    name: 'Heroes',
    useAsDefault: true,
    component: HeroListComponent },
{   path: '/hero/:id',
    name: 'HeroDetail',
    component: HeroDetailComponent }
])
export class AppComponent {}
```
```html
<!-- Routed views go here -->
<router-outlet></router-outlet>
```

----
### Routing: defining in main app component

```ts
import { RouteConfig, ROUTER_DIRECTIVES, ROUTER_PROVIDERS }
    from 'angular2/router';

@Component({
    selector: 'my-app',
    template: `
        <a [routerLink]="['Heroes']">Heroes</a>
        <a [routerLink]="[’CrisisCenter']">Crisis Center</a>
        <router-outlet></router-outlet> `,
    directives: [ROUTER_DIRECTIVES],
    providers: [ ROUTER_PROVIDERS, HeroService ]
})
@RouteConfig([
    { path: '/heroes', name: 'Heroes', component: HeroesComponent }
])
export class AppComponent {}
```

----

## Routing: heroes component

```ts
@Component({
    selector: 'my-heroes',
    templateUrl: 'app/heroes.component.html',
    styleUrls:  ['app/heroes.component.css'],
    directives: [HeroDetailComponent]
})
export class HeroesComponent implements OnInit {
    heroes: Hero[];
    selectedHero: Hero;
    constructor( private _router: Router,
       private _heroService: HeroService) {}
    getHeroes() {
        this._heroService.getHeroes().then(heroes =>
           this.heroes = heroes);
    }
    ngOnInit() { this.getHeroes(); }
    onSelect(hero: Hero) { this.selectedHero = hero; }
    gotoDetail() {
	this._router.navigate(['HeroDetail', { id:
                               this.selectedHero.id }]);
    }
}
```
<!-- .element: class="largercode" -->

----
## Routing: heroes template

```html
<h2>My Heroes</h2>
<ul class="heroes">
    <li *ngFor="#hero of heroes"
        [class.selected]="hero === selectedHero"
        (click)="onSelect(hero)">
        <span class="badge">{{hero.id}}</span> {{hero.name}}
    </li>
</ul>

<div *ngIf="selectedHero">
    <h2>
        {{selectedHero.name | uppercase}} is my hero
    </h2>
    <button (click)="gotoDetail()">View Details</button>
</div>
```

<p class="current-visible"
style="position:absolute; left:700px; top:250px;">
<img src="resources/angular2/img10.png" width="80%"></p>

----
## Routing: hero details component

```ts
@Component({
    selector: 'my-hero-detail',
    templateUrl: 'app/hero-detail.component.html',
})
export class HeroDetailComponent implements OnInit {
    hero: Hero;
    constructor(
        private _heroService: HeroService,
        private _routeParams: RouteParams) {
    }
    ngOnInit() {
        let id = +this._routeParams.get('id');
        this._heroService.getHero(id)
            .then(hero => this.hero = hero);
    }
}
```
app/hero-detail.component.html

----
## Routing: hero details template

```html
<div *ngIf="hero">
    <h2>{{hero.name}} details!</h2>
    <div>
        <label>id: </label>{{hero.id}}</div>
    <div>
        <label>name: </label>
        <input [(ngModel)]="hero.name" placeholder="name" />
    </div>
    <button (click)="goBack()">Back</button>
</div>
```
hero-detail.component.html

----
##  Using pipes

```ts
import {Component} from 'angular2/core'

@Component({
    selector: 'hero-birthday',
    template: `<p>The hero's birthday is
               {{ birthday | date }}</p>`
})
export class HeroBirthday {
    birthday = new Date(1988,3,15); // April 15, 1988
}
```

----
## Define custom pipe

```ts
import {Pipe} from 'angular2/core';

/* Raise the value exponentially
* Takes an exponent argument that defaults to 1.
* Usage: value | exponentialStrength:exponent
* Example:
*   {{ 2 |  exponentialStrength:10}}
*   formats to: 1024
*/
@Pipe({name: 'exponentialStrength'})
export class ExponentialStrengthPipe {
  transform(value:number, args:string[]) : any {
    return Math.pow(value, parseInt(args[0] || '1', 10));
  }
} 
```

----
## Use custom pipe

```ts
import {Component} from 'angular2/core';
import {ExponentialStrengthPipe} from './exponential-strength.pipe';

@Component({
  selector: 'power-booster',
  template: `
    <h2>Power Booster</h2>
    <p>
     Super power boost: {{2 | exponentialStrength: 10}}
    </p>
    `,
  pipes: [ExponentialStrengthPipe]
})
export class PowerBooster { }
```

----
## Use Async pipe

```ts
import {Component} from 'angular2/core';

// Initial view: "Message: "
// After 500ms: Message: You are my Hero!"

@Component({
selector: 'hero-message',
template: 'Message: {{delayedMessage | async}}',
})
export class HeroAsyncMessageComponent {
  delayedMessage:Promise<string> =
  new Promise((resolve, reject) => {
     setTimeout(() => resolve('You are my Hero!'), 500);
  });
}
```
