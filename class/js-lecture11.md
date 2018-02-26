## ES 6

### `let` and `const` and `var`

when it comes to `variable`
- data type : primitive? object?
- pass by value?, pass by reference?
- hoisting? scope and closure


---

## `let`

### `var`의 문제점

- `var` 는 block level scope를 지원하지 않는다.(다른 언어와 차이점)
- 전역변수는 의도치 않게 변경 혹은 중복될 수 있으므로 피해야 한다.(name space가 오염된다)
- 전역변수는 실행컨텍스트의 동작방식(선언과초기화 동시에 일어남)에 따라 변수 hoisting이 발생한다.

### `let`의 특징

- block level scope지원 (if, for, function)
- 중복선언 허용하지 않는다 (syntax error)
- `let` 키워드 생략 불가능
- hoisting이 안되는 것 처럼 동작한다.(TDZ)
- window.foo = let foo는 같이 않다. (var변수는 같음)


### Hoisting

1. 선언 단계
2. 초기화 단계
3. 할당 단계

선언 - 초기화가 따로 일어난다.
선언하기 전에는 참조할 수 없음.
let은 실행컨텍스트에는 있지만 메모리에는 없음
const도 동일하게 작동

### Closure

- 자유변수!

```js
var funcs = [];

// 함수의 배열을 생성한다
// i는 for loop에서만 유효한 지역변수이면서 자유변수이다
for (let i = 0; i < 3; i++) {
  funcs.push(function () { console.log(i); });
}

// 배열에서 함수를 꺼내어 호출한다
for (var j = 0; j < 3; j++) {
  funcs[j]();
}
```

---

## `Const`

- 재할당이 불가능하다 => 선언과 동시에 초기화해야한다.
- 선언문과 초기화를 쪼갤 수 없다.
- 상수(변하지 않는 수)를 위해서 만들어 짐

```js
const FOO; // Syntax Error
const BAR = 123;
BAR = 456; //Type Error
```


- 상수에만 사용하지 않는다.!!
- 객체 타입에는 const를 쓰는게 좋다. -> 재할당을 안하는게 좋다. 
- 의도적으로 주소가 바뀌는 경우에는 let사용
- 객체는 기본적으로는 주소가 바뀌지 않는다.

```js
const obj = { foo: 123 };

const user = {
  name: 'Lee',
  address: {
    city: 'Seoul'
  }
};

user.name = 'Kim';  //이렇게 해도 참조가 바뀌지 않으므로 const써도 무관
```

---

### usage

- es6에서는 `var`를 쓰지 않도록 한다.
- `let` : 재할당이 일어나는 경우 사용
- `const` : 재할당이 필요없는 경우 사용 (객채타입, 상수)

---

## Template Literals

- backtick ``

---


## Arrow Function

- 콜백대용으로 쓴다
- 무명으로 사용한다 (따라서 일반적으로 쓸때는 no!)

```js
function (x) {
    return x * x;
}

x => x * x

//  중괄호 생략가능 { return x * x }, 세미콜론도 생략가능
//  한줄코드는 return 생략해도 암묵적으로 자동 리턴한다.
```


### this

- 함수에서 this는 기본적으로 window전역을 가리킨다.
- arrow function 에서는 this는 자기 자신의 바루 위 컨텍스트를 가리킨다.

- this를 전달해서 사용하고 싶으면, 
    1. 고차함수 this Arg지정
    2. bind, apply 사용
    3. 콜백으로 array function사용 (this는 자신의 바로 위 컨텍스트가  this)

- arrow function은 객체내부에서 매서드로 사용할때는, this에 주의
- arrow function은 이벤트 리스너 콜백으로 사용할때는, this에 주의한다.(e.currentTarget);

**어디든 this를 사용해야 할 경우에는 arrow function은 주의가 필요하다.**


