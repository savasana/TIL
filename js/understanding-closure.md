## Understanding closures

### scope

- scope controls the visibility and lifetimes of variables and parameter.
- **lexical scope** is based on where variables and blocks of scope are authored, by you, at write time, and thus is set in stone by the time the lexer processes your code.
- scope loop-up stops once it finds the **first match**


```js
//collision in overwriting of values
function foo() {
  function bar(a) {
    i = 3; 
    // changing the `i` in the enclosing scope's for-loop
    console.log( a + i );
  }

  for (var i = 0; i < 10; i++) {
    bar( i * 2 ); 
    // infinite loop 
  }
}

foo();
```

### closure

- closure is when a function **remembers** its lexical scope even when the function is executed outside that lexical scope
- inner functions get access to the parameters and variables of the functions they are defined within


**execution context**
- there are 3 types of execution context in JS
- Global Execution Context, Functional Execution contex, Eval 
- 

[Execution context, Scope chain and JavaScript internals](https://hackernoon.com/execution-context-in-javascript-319dd72e8e2c)

---

```js
//closure examples

function foo() {
  var a = 2;

  function bar() {
    console.log( a ); 
  }
  
  return bar;
}

var baz = foo();
baz(); // 2 

```

  - the function is being invoked weel outside of its author-time lexical scope. closure lets the function continue to access the lexical scope it was defined in at author-time.

---

```js
  function wait(message) {
      setTimeout( function timer(){
        console.log( message );
      }, 1000 );
  }

  wait( 'hello, closure!' );
```
  - engine goes to invoke that function, which is invoking out inner `timer` function, and the lexical scope reference is still intact.

---

```js
function greet(whattosay) {
  return function(name) {
    console.log( whattosay + '' + name );
  };
}

var say = greet('hi' );
say('yohan');
```

  - `say()` function execution context | `name = 'yohan'` 
     needs value of whattosay -> looks for outer scope(when it was written) -> greet() has `whattosay = 'hi'`
  - `greet()` function execution context | `whattosay = 'hi'`
  - globel execution centext |`say()`



---


```js

function buildfunctions() {
  var arr = [];

  for (var i = 0; i < 3; i++) {
    arr.push(
      function() {
        console.log( i );
      }
    )
  }

  return arr;
}

var fs = buildfunctions();

fs[0]();  //3
fs[1]();  //3
fs[2]();  //3

```
  - `fs[0]()` execution context | i? look for the value in memory of its outer environment reference -> buildfunctions -> i : 3
  - `buildFunctions()` execution context | `i = 3` , `arr[f0,f1,f2]`
  - global execution context | `buildFunctions()` , `fs`


```js
//solution - using let (add block scope)
function buildfunctions() {
  var arr = [];

  for (let i = 0; i < 3; i++) {
    // it creates a new i for each iteration. 
    arr.push(
      function() {
        console.log(i);
      }
    )
  }

  return arr;
}

var fs = buildfunctions();

fs[0]();  //0
fs[1]();  //1
fs[2]();  //2
```

