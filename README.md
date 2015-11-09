# Little test with vueify

Browserify transform for Vue.js components, with scoped CSS and component hot-reloading.
https://github.com/vuejs/vueify


## index.html
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title></title>
    </head>
    <body>
        <app></app>
        <app msg="Hello world! How are you ?"></app>
        <app></app>
         <script src="build/build.js"></script>
    </body>
</html>
```

## src/main.js
```javascript
var Vue = require('vue')
var App = require('./app.vue')

new Vue({
  el: 'body',
  components: {
    app: App
  }
})
```

## src/app.vue
```html
<style>
    .red {
        color: #f00;
        }
</style>

<template>
    <h1 class="red">{{ msg }}</h1>
</template>

<script>
module.exports = {
    props: ['msg'],
    data: function () {
        return {
            msg: 'Hello world!'
        }
    }
}
</script>
```

```

npm install
browserify -t vueify -e src/main.js -o build/build.js
```
