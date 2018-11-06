## The Progressive JavaScript Framework

<div align="center"><img src="resources/framework/vuejs-logo.jpg" width="70%"></div>

----
# Vue is easy

### Reactive web development concepts

----
## Templates and Data Binding

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>

<div id = "app">
{{message}}
</div>
```

```js
var app = new Vue({
  el: '#app',
  data:{
    message : 'hello Vue!'
  }
})
```

----
## Playing with the DOM


```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>

<ul id="example-1">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>
```


```js
var example1 = new Vue({
  el: '#example-1',
  data: {
    items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
  }
})
```

----

## Two-Way Data Binding



```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>

<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
```

----

## Two-Way Data Binding



```html
<select v-model="selected" multiple>
  <option>A</option>
  <option>B</option>
  <option>C</option>
</select>
<br>
<span>Selected: {{ selected }}</span>
```

----
## Transition Effects

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>

<div id="demo">
  <button v-on:click="show = !show">
    Toggle
  </button>
  <transition name="fade">
    <p v-if="show">hello</p>
  </transition>
</div>
```

```js
new Vue({
  el: '#demo',
  data: {
    show: true
  }
})
```
```css
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0
}
```



----
# Vue can be easily integrated

### LARGE or small


----
## Components
<div align="center"><img src="resources/framework/img7.png" width="100%"></div>


----
## Components

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>
<div id="example">
  <my-component></my-component>
</div>
```

```js
// register
Vue.component('my-component', {
  template: '<div>A custom component!</div>'
})
// create a root instance
new Vue({
  el: '#example'
})
```

----
# Clean and Simple

----
## Clean and Simple
- Vue was created by Evan You after working for Google on AngularJS. You later summed up his thought process,

> I figured, what if I could just ** extract the part that I really liked** about Angular and build something **really lightweight** without all the extra concepts involved?
