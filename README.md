# VueJS Concept Sheet

## v-bind
> Dynamically binds an attribute to an expression

```javascript
    const app = new Vue({
        el: '#app',
        data: {
            heroImage: './assets/hero.jpg'
        }
    })
```
```html
    <img v-bind:src="heroImage" />
```


Shorthand syntax
```html
    <div :img='' />
    <div :alt='' />
    <div :href='' />
    <div :title='' />
    <div :class='' />
    <div :style='' />
    <div :disabled='' />

```


## Conditional rendering

v-if-else-if
> Removes/adds the element to the DOM

```javascript
    var inStock = false
    var inventory = 23
```
```html
    <div v-if="inventory >= 1"></div>
    <div v-if-else="inventory === 1"></div>
    <div v-else="inStock"></div>
```

v-show
> Simply hides the element in the DOM with inline style 
```javascript
    var inStock = false
```
```html
    <div v-show="inStock" style="display: none;"></div>
```



## Lists

Example
```javascript
    gallery: [
        {
            id: 0,
            name: 'Portrait #1',
            price: 325532,
        },
        {
            id: 1,
            name: 'Portrait #2',
            price: 325532,
        },
        {
            id: 2,
            name: 'Portrait #3',
            price: 325532,
        }
    ]
```
```html
    <ul>
        <li v-for="item in gallery" :key="item.id">
            {{ item.name }}
            {{ item.price }}
        </li>
    </ul>

```


## Event Handling

```html
<button v-on:click="addToCart">Add to cart</button>
<button v-on:click="clearCart">Clear cart</button>
Cart ({{ cart }})
```

Add methods to the methods object.
```javascript 
const app = new Vue({
    el: '#app',
    data: {...},
    // Methods
    methods: {
        addToCart: function() {
            this.cart += 1
        },
        clearCart: function() {
            this.cart = 0
        }
    }

```