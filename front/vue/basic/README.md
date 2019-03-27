# Vue.js Basic

## CDN
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Vue Sample</title>
  </head>
  <body>
    <div id="app">
      {{ message }}
    </div>

    <script src="https://unpkg.com/vue"></script>
    <script>
      new Vue({
        el: '#app',
        data: {
          message: 'Hello Vue.js!'
        }
      })
    </script>
  </body>
</html>

```