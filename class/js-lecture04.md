# Lecture 04

### why learning Prototype?
Javascript - 멀티패러다임 언어
명령형 , 함수형, 프로토타입 기반 객체 지향


### prototype
프로토타입 객체의 리소스를 공유한다.
무엇을 공유? - method의 내용이 같은것을 공유

모든 객체는 자신의 **부모 역할**을 담당하는 객체와 연결되어 있다.부모 객체의 property또는 method를 상속받아 사용할 수 있다. 이러한 객체를 Prototype객체 라고 한다.


Prototype객체는 생성자 함수에 의해 생성된 각각의 객체에 공유 프로퍼티를 제공하기 위해 사용

` [[Prototype]] 같은것 __proto__ `

[[Prototype]] : 함수 포함 모든 객체가 가지고 있는 프로퍼티
prototype 프로퍼티 : **함수 객체만 가지고 있는 프로퍼티**



---


## Scope

자바스크립트는 진입점(시작점)이 없다. 쓰는순간 다 실행. 
지역 Global / 지역 Local

### global scope :  전체영역 / 어디에서든지 참조할 수 있다.

코드 블록 `{ }` 을 지역으로 인정하지 않는다.
단, function level scope은 지역
let에 의한 보완 - es6

### why 지역변수?
- life-cycle 
- 메모리를 효울적으로 사용할 수 있다.

---

## This
- this는 언제나 전역 개체이다. 
- 단 2가지 케이스만 빼고  method내에 있을때 혹은 생성자함수 안에있는 this경우만 빼고 다 전역 객체이다.

- callback에 있을때 -> 전역
- 일반 함수 -> 전역

























