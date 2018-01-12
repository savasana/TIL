# day 05

## Teacher says
>Hand Coding!
>Brain Compile!
>Eye Decoding!


## Web Programming
**Static vs Dynamic**
- Static : Each contents have to have an each page
- Dynamic : Display different content from the same source code.Interaction 

### Transformation of Web Development Pattern
Static -> Static Client + Dynamic Server -> Dynamic Client & Server **(now)**

```html
    <html>
    <head>
    <script src="https://unpkg.com/vue"></script>
    </head>
    <body>
    <h1>{{ header }}</h1>   //interaction with server
    <div id="app">
    {{ message }}
    </div>
    <script>
    var app = new Vue({
    el: '#app',
    data: {
        message: '안녕하세요 Vue!'
    }
    })
    </script>
    </body>
    </html>
```



