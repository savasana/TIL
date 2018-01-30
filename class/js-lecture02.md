# Javascript Lecture 02



### Syntax Basics

Expression(표현식) - 하나의 값으로 평가. 5 * 10 , 'hello'+'world'
Statement(구문) - 5 * 10; / var x; / if (y > 0){ ~~ }


### variables

프로그래밍에서의 수 = 정수 , 실수(.xxx)
값을 저장, 참조하기 위한 목적. 위치(주소)를 기억하는 저장소.
**memory address**

#### Dynamic type
( vs Static Type)


### 2 types
- Primitive data type (Boolean, null, undefined, number, string, symbol)
- Object type (object)


### keyword

- THE COMMON SENSE!!
- 약속, 문법
`var` `while` `function` 


### comment
- 원활한 의사소통을 위해
- 간단, 명료하게 작성할 것
- 코드 자체가 주석이 되면 최고
- 변수명, 함수명, 프로터피명 작성할때 신경쓸것 
- 주어, 목적어, 서술어


---


### data type

**memory**

`var a;` 
-> 변수 선언 -> 메모리에 공간을 확보 -> 얼마나? 최소단위로 확보 -> 어떤데이터? 
js는 동적타입 언어라서 어떤 데이터 타입이 들어올지 알 수 없다. (타 언어와 다른점)
어떤 값이 올지 모르기 때문에 일단 `undefined`타입을 메모리에 입력해 놓고(동적 언어이기 때문에 발생하는 어쩔 수 없는 삽질), 할당문 `a = 10;` 을 만났을때 **새롭게 자리를 만들고** 거기에 10값을 주고 여기를 가리킨다.(point)

**프로그래밍은 변수를 통해 값을 저장하고 참조하며 연산자로 값을 연산, 평가하고 조건문과 반복문에 의한 흐름제어로 데이터의 흐름을 제어하고 함수로 재사용이 가능한 구문의 집합을 만들며 객체, 배열 등으로 자료를 구조화하는 것이다.**

변수는 위치(주소)를 기억하는 저장소.(값은 그때 그때 가서 확인)
변수는 **memory address**에 접근하기 위한 수단 -> 16진수 의미 없는 숫자를 사람이 이해할 수 있게 만든 식별자. 

```js
 var age = 10;
// age는 사람이 이해할 수 있게 만든것. (+원래 주소를 가지고 있음.)
// age라는 주소를 찾아가서 10을 확인한다. 
```

8bite 크기를 가지고 있고 이는 일반적으로 쓸 수 있는 수를 다 담을 수 있다.
(은행권등 상상초월의 수를 사용하는 경우 새롭게 제작해 사용)


---

###  Primitive Data Type
- **immutable value**
- **pass by value**

**Boolean**
- true / false 논리값
- 0, null, undefined : false

**null**
- 참조를 지울 때 사용.
- null은 null만 가질 수 있다.


**undefined**
- 값을 할당하기 전 미리 초기화
- hoisting 과 연결


**Number**
- 8byte로 정수+실수의 숫자형 
- 0, +무한대, -무한대, NaN(not a number, 문자+숫자했을때 등.)
- 타언어는 메모리를 효율적으로 관리하기위해 다양한 숫자 타입 존재.


**String** 
- 문자열 
- 16비트(2byte) 부호없는 정수 값
- `"~"`, `'~'` js에서는 주로 `'~'`사용 
(에디터에 ESLint 사용해서 convention 지정하면 유용)

**Symbol**
- es6 에서 추가됨 



### Object type
- mutable, changeable
- pass by **reference**


--- 

### Memory Segmentation

- Code 
- Data
- Stack (LIFO) : 일반 선언 값 - 데이터 타입에 따라 딱 정해져있음
- Heap : 참조형 값 - 데이터가 늘어나고 줄어들 수 있어

( code - data - stack - heap ) : C언어 기준의 구조
js에서의 전역변수는 window의 property -> 아마 heap 일것이다.

---

### String
- 문자열은 배열처럼 인덱스를 통해 접근 가능 **유사배열**
- 순회하는 성질 **for문으로 돌릴 수 있다**



---
### pass by value (primitive data type)
- 변경 불가능하지만 **재할당**은 가능하다.
- 가리키는 곳의 주소를 전달하는게 아닌 그 주소가 가진 값을 **복사**해서 새로 주는 것. (=value)


```js
var a = 1;
var b = a; -> a의 값을 복사하는것. 

a = 10;
console.log(b); //1 

```
### object type 
자바스크립트는 객체(object)기반의 스크립트 언어로서 자바스크립트를 이루고 있는 거의 “모든 것”이 객체이다. 기본자료형(Primitives)을 제외한 나머지 값들(배열, 함수, 정규표현식 등)은 모두 객체이다. 또한 객체는 pass-by-reference(참조로 접근)이며 메모리의 힙 영역(Heap Segment)에 저장된다


---

### variable

`var` : es5 
`let` `const` : es6

변수 이름 네이밍 방법
- Camel Case : firstName (주로 이렇게 쓴다)
- Snake : first_name


- 변수의 중복 선언이 가능
- var 키워드 생략 허용

---
### dynamic typing

할당 시점에 데이터 타입을 결정한다.
(동적타입의 문제점을 보완하기 위해서 나온게 타입스크립)


---

### variable hoisting
- 변수를 선언하기 이전에 참조할 수 있는것 (**입사 단골 문제**)
- 함수의 코드블럭은 지역변수로 인정 (나머지는 전역)


---
### var 의 문제점
- 전역이 하나로 전역변수는 조심해서 사용할것 - 사용 억제!


---
## 연산자

### 산술연산자

x = 5;
z = x++ : 선대입후증가 -> 5
z = ++x : 선증가후대입 -> 7

+ 결합연산
'a' + b : 둘 중 하나가 문자일 경우 결합 후도 문자열
'5' + 5 = '55';
'hello' + 5 = 'hello5'


### 비교연산자

 `==` , `!=` 동등비교연산자. 사용자제
 `===` , `!==` 값과 타입 둘 다 확인


### 삼항연산자 (ternary operator)
if문을 한줄로 표현 가능/ 단 한줄을 넘어가는 경우 안쓰는게 좋아(가독성 떨어짐)

```js 
var condition = true;
var result = condition ? 'true' : 'false';
```

### 논리 연산자
`a && b` 
-> a가 true이면 b return
-> a가 false이면 a return

`a || b `
-> a가 true 이면 a return
-> a가 false 이면 b return



```js
function foo (str) {
  str = str || '';
  // str에 undefined가 들어왔음 = false 
  // falst || '' 
  // '' 값을 리턴
  // do somethig with str
  console.log(str.length);
}

foo();     // 0  초기화, 에러방지
```


---

### type operators
- typeof : null 설계오류 유의
- instanceof : 객체에서 사용 용어

---

## Control Flow (제어문)


### Block statement
- 구문을 그룹핑 : 같이 실행되어야 의미있는 애들을 묶는다.
- 함수 , while, obj

### Conditional
- if statement : 참, 거짓으로 구별
- switch statement : break없으면 다음 case 계속 실행!

### Loop
- for, while, do while 
- 실제로는 for 보다 고차함수(map, filter, foreach, find,..)를 많이 쓴다 하지만 기본중의 기본!


#### for statement

```js
for ([초기문]; [조건문]; [증감문]) {
  구문;
}
```

---

