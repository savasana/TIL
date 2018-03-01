## Extended parameter handling

---

### Default Parameter Value



---

## Class

### ES6클래스는 class키워드를 사용하여 정의

```js
class Person {
    constructor(name) {
        this._name = name;
    }
    sayHi() {
        console.log('HI! ${this._name}');
    }
}

const me = new Person('Lee');
me.sayHi();

```


### 인스턴스 생성하려면 new 연산자와 함께 생성

```js
class Foo {}

const foo = new Foo();
```

- constructr는 인스턴스를 생성하고 초기화하기 위한 특수 method
- 클래스 내에 한 개만 존재할 수 있으며 만약 클래스가 2개 이상이면 에러.
- constructor 생략 가능.

---

### 멤버 변수

```js
class Foo {
  constructor(name) {
    this.name = name; // 멤버변수의 선언과 초기화
  }
}

const foo = new Foo('Lee');
console.log(foo.name); // Lee
```

- 클래스 바디에는 메소드만을 포함할 수 있다. 바디에 멤버 변수를 선언하면 에러 발생
- constructor 내부에서 선언한 멤버 변수는 언제나 public이다. 외부 참조 가능
- 감추는 방법 있지만 난해하다 그래서 type script를 쓰라는 것

---

### Hoisting

- let, const, class는 1,2,3단계 (선언, 초기, 할당)의 단계가 각각 일어난다.
- 선언문 이전에 참조하면 TDZ에 빠져서 에러가 난다. (var, 혹은 일반 함수와 다름)

---

### getter, setter

- get 은 반드시 리턴이 있어야하고
- set 은 매개변수값 필요
- property처럼 사용 

- 매서드로 만들어서 사용해도 됨 - 같은 방식.
- 프로퍼티처럼 사용할 수 있어서 유용할 때가 있음.

```js
class Foo {
  constructor(arr = []) {
    this._arr = arr;
  }

  // getter: firstElem은 멤버 변수 이름과 같이 사용된다.
  // getter는 반드시 무언가를 반환하여야 한다.
  get firstElem() {
    return this._arr.length ? this._arr[0] : null;
  }

  // setter: firstElem은 멤버 변수 이름과 같이 사용된다.
  set firstElem(elem) {
    // ...this._arr은 this._arr를 개별 요소로 분리한다
    this._arr = [elem, ...this._arr];
  }
}

const foo = new Foo([1, 2]);
// 프로퍼티 firstElem에 접근하면 getter가 호출된다.
console.log(foo.firstElem); // 1

foo.firstElem = 100;
console.log(foo.firstElem); // 100
```


---

### 정적 메소드 

- static 키워드는 정적 메소드를 정의한다.
- 범용적인 함수들을 static으로 만든다
- Math 객체의 메소드와 같이 전역에서 사용한 유틸리티 생성하는데 사용

```js
class Foo {
  constructor(prop) {
    this.prop = prop;
  }

  static staticMethod() {
    return 'staticMethod';
  }

  prototypeMethod() {
    return 'prototypeMethod';
  }
}
```
