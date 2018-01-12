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

## Web Browser

- parsing : reading / processing the HTML
- rendering : parses HTML, CSS and displays the content on the screen

Mosaic / Netscape / Internet Explorer/ FireFox / Chrome(2008)

parsing 과 rendering => 연산 => 연산은 엔진이 중요!
Chrome에 내장된 v8 Enging이 역사적으로 중요한 역할(js를 한단계 업하는 역할을 함)



**PWA : Progressive Web Apps**
**notification, offline available (via service tools)**