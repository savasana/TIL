### IIFE Function

```js
function foo() {
  if (true) {
    var secret = 'secret information';
    ...
  }
  console.log(secret);
}
foo();
// secret information!!
```
위의 코드와 같이 변수 `secret`은 if문 뿐만 아니라 전체 `foo()`함수 내에서 접근 가능하다. IIFE함수로 감싸면 새로운 function scope가 형성되어 함수 외부에서는 참조할 수 없다.

```js
function foo() {
  if (true) {
    (function() {
      var secret = 'secret information'
    }());
  }
  console.log(secret);
}
foo();
// Reference Error: secret is not defined
```


