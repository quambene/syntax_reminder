# Vue

- [Template](#template)
- [Directives](#directives)
- [Input binding](#input-binding)
- [Event handling](#event-handling)

### Template

```html
<div id="myApp">  
    {{ message }}  
</div>
```

### Directives

```html
<div v-if="isVisible"></div>
<div v-once>{{ permanent message}}</div>
<div v-bind:class="{ 'is-active': isActive }"></div>
<input v-model="message">  <!-- two way data binding -->
<button v-on:click="doSomething"></button>

 <!-- Dynamic argument -->
<a v-bind:[attributeName]="url"></a>

 <!-- Modifier -->
 <form v-on:submit.prevent="onSubmit"></form> <!-- call event.preventDefault() -->

<!-- Shorthand -->
<div :class="{ 'is-active': isActive }"></div> 
<button @click="doSomething"></button>
```

```javascript
var app = new Vue({  
    el: '#app',  
    data: {  
        isVisible: true,
        isActive: false,
    }  
})
```

### Input binding

```html
<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
```

### Event handling

```html
<button v-on:click="myClickHandler">Click me!</button>  
```

```javascript
var app = new Vue({  
    el: '#app',  
    methods: {  
        myClickHandler: (event) => {  
            console.log('Button clicked!');  
        }  
    }  
})
```
