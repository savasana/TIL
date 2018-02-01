# JavaScript Lecture 03

- 내가 쓴 코딩이 작동되면 왜 되는지 설명할 수 있어야 한다.
- 기술부채를 늘리지 말것.
- 사소한 것에서 부터 꼼꼼하게 하는 습관을 들이자.
- 이해가 될 때까지 반복할것.
- 코딩 컨벤션에 주의하고 일관성있게 코딩할것.

---
‘값을 평가한다? ‘ -> 값이 참인지 거짓인지 판단한다


### control flow
흐름제어를 하기 위해서는 true,false로 판단 될 수 있는 조건식(expression)이 필요하다.
자바스크립트는 강제 형 변환을 시켜준다. (coercion) -> 암묵적 강제 형 변환

truthy value & false value
Truthy value : 1, 
Falsy value : 0, Null, undefined,  NaN,  ‘’ 

`+` 는 산술 과 결합연산자 두가지 역할



---

#### primitive types
- immutable
- pass by value

---

#### checking existence

```js
var elem = document.getElementById('header');

if (elem) { 
	//요소가 존재함
} else {
	//요소가 존재하지 않음 - 에러메세지
}

if (elem == true)
// if (elem) 과 다른 개념이다
// elem 의 value를 평가하는것.

```


---

## Object
객체는 데이터를 갖고, 그 데이터와 관련된 동작을 가진다.
property & method (값으로 함수를 가지고 있으면 method라고 한다) 
name and value pair

객체의 데이터 -> 관심있는 대상만 입력하는 추상화를 거친다.

상속 ( 부모 꺼는 내꺼, 내꺼는 내꺼 )
부모의 자원(property, method)을 자식(손자,…)이 쓰는 것.

prototype -> 상속을 표현하는 방법
일반적인 class 용어는 : class 와 class와의 관계를 맺어준다 (개별적인 존재. 입양 같은거)
js에서의 프로토타입 -> 부모 자식 - 긴밀하게 연결

### property 
property name(key) : 기본은 문자(숫자를 적으면 문자로 자동 변형) / 빈 문자와 숫자도 가능/“” 생략 가능/ 
항상 값이 존재 (undefined 제외한 모든 값)

property는 obj의 자원(resource)

### method
함수. 객체 안에 있을때 method 라고 한다.


### 객체 생성 방법
3가지 ( 객체리터럴, 오브젝트생성자, 생성자 함수만들기)

1. 객체 리터럴 (literal) - 가장 일반적인 방식
단일로 쓰일때 유용. 여러개 만들때는 비효율 

```js
var person = {
	name: ‘lee’
}
```

2. 생성자 함수 - (객체를 생성하는) 
브라우저 내장 함수 built-in function
틀을 같지만 데이터가 다른 객체 여러개 생성해야 할때 유리.

```js
var person = new Object();
//빈 객체를 생성 - boolean : true;
```

함수는 정의해두고 필요할때 호출해서 사용한다.
호출하지 않으면 실행되지 않는다.
생성자함수의 목적은 객체를 만드는것.
객체를 만들때는 new 연산자와 함께 생성자 함수를 호출한다.

this ->  생성자 함수가 생성한 객채 자기 자신

매개변수 : 함수호출에서 값을 받아서 함수로 전달하는 인터페이스 역할.

다양한 패턴 존재 

---

### 객체 프로퍼티 접근

객체의 프로퍼티는  객체 소유이므로, 객체를 경우해서 접근.
객체 이름은 객체 value를 설명해줄 수 있어야한다.

- 마침표 표기법 - 객체이름.프로퍼티명 / 기본!
- 대괄호 표기법 - 객체이름[“프로퍼티명”] / 괄호안에 반드시 문자열로 만들어줘야함. “”없으면 변수로 인식해서 변수를 찾으려고 한다.


---


기본타입은 값을 갖고, ,객체는 참조를 갖는다.

```js
var person = {
  'first-name': 'Ung-mo',
  'last-name': 'Lee',
  gender: 'male',
};

person['first-name'] = 'Kim';
console.log(person['first-name'] ); // 'Kim'

```


---

### 프로퍼티 동적생성
빈객체에 추가추가 추가


### side effect
// 객체의 어떤 값을 바꾸면 그걸 가르치는 애들도 영향을 받는다.
// 사이드 이펙트가 없는 함수를 순수 함수  지향.
// 사이드 이펙트가 있는 함수는 비순수 함수 


---
// 만드는애 -> 생성자 
// 생성자가 바로 생성해 낸 객체 -> instance


---

## 함수 function
효율 - 유지보수에 유리하다
코드가 중복되면 가동성이 나빠 **가독성**이 나쁘면 독해가 어려워
독해가 어려우면 오류가 발생해
남을 배려해서 코딩을 작성하자

- 함수는 객체
- 함수는 호출할 수 있다
- 함수는 일급 객체이다(중요)

```js
function square(number){
	return number * number;
//표현식(number*number)의 값을 이 함수의 결과로 반환한다.
}
```

### 매개변수 : 
0개 이상의 리스트
var 없이 그 자체가 선언


### 함수 표현식 expression

일급 객체의 특징
- 무명의 리터럴로 표현이 가능하다.
- 변수나 자료 구조에 저장할 수 있다.
- 함수의 parameter 로 전달할 수 있다. (매개변수로)
- 반환값으로 사용할 수 잇다.


reference error
- 선언하지 않은 변수에 접근하면 오류



함수명이 변수명이 된다.

```js
var square = function square(number) {
  return number * number;
};
```

### 변수 호이스팅 variable hoisting
- 실행컨텍스트!!!를 알아야해 중요중요
- 코드는 미리 한번 엔진이 훝어보고 var, function 은 VO (variable Object)에 미리 적어놓는다 -> 선언 단계.

1. 선언 -> 메모리로 가지않아. 실행컨텍스트의 VO에 적어두는것. 참조 가능하다.
2. 초기화 -> 메모리로 접근해서 undefined로 용량 확보
3. 할당 


### 함수 호이스팅
1,2,3단계를 한번에 한다.
참조 가능하고 값도 들어있고 이전에 실행도 가능.

표현식 선언식
선언식은 여기저기 참조가능
함수 표현식은 변수호이스팅을 따른다.

자바스크립트는 ES6의 let, const를 포함하여 모든 선언(var, let, const, function, function*, class)을 호이스팅(Hoisting)한다.

---


### 매개변수 parameter vs argument



---
### 가변 인자 함수 
인자 parameter



---
### callback

```js

function foo(func) {
  var res = func();
  return res;
}

function bar() {
  return 'caller : ' + bar.caller;
}

console.log(foo(bar)); // function foo(func) {...}
console.log(bar());    // null (browser에서의 실행 결과)
```


유사배열 객체 특징 -> length -> 순회(for 문) 가능
array like object

---





