# Lecture 04
### prototype
프로토타입 객체의 리소스를 공유한다.
무엇을 공유? - method의 내용이 같은것을 공유


### why learning Prototype?
Javascript - 멀티패러다임 언어
명령형 , 함수형, 프로토타입 기반 객체 지향


property
__proto__

---

### IIFE 
즉시호출함수


---

### Callback function
나중에 호출할게


---

### Prototype


---

## Scope
자바스크립트는 진입점(시작점)이 없다. 쓰는순간 다 실행. 
### global scope :  전체영역 / 어디에서든지 참조할 수 있다.

코드 블록 `{ }` 을 지역변수로 인정하지 않는다.
단, function level scope  (함수만 지역 가질 수 있다.)

### why 지역변수?
- life-cycle 
- 메모리를 효울적으로 사용할 수 있다.


### 전역변수 최소화


---

## This
- this는 언제나 전역 개체이다. 
- 단 2가지 케이스만 빼고  method내에 있을때 혹은 생성자함수 안에있는 this경우만 빼고 다 전역 객체이다.

- callback에 있을때 -> 전역
- 일반 함수 -> 전역
- 























