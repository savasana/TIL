### built-in object

내장 객체 - 웹페이지 등을 표현하기 위한 공통의 기능을 제공한다.

### What is API?

- Application Programming Interface
- 다양한 소프트웨어 부분들(components)사이의 communication을 위한 방법을 정의한것?
- set of defined methods of communication between various software components.
- 다양한 API가 있다. OS, web-based system, database system, computer hardware or software library, ...
- 프로그래밍언어를 통해 -> OS가 일을 해주는것 ( OS가 일을 하도록 하는 것을 간소화 시킨것이 프로그래밍 언어 )
- User Interface : 사용자가 컴퓨터와 이야기 하는 방식을 인터페이스 라고 이해하자.


> Just as a graphical user interface makes it easier for people to use programs, application programming interfaces make it easier for developers to use certain technologies in building applications. By abstacting the underlying implementation and only exposing objects or actions the developer needs, an API simplifies programming.
> [wikipedia](https://en.wikipedia.org/wiki/Application_programming_interface)


### Native Object

- Native Object : browse관련된 것. ( 화면, 프론트엔드 )
- 화면 내에 표시되는 것들을 Document라고 한다
- 

### BOM



window.location 

Location()생성자 함수  -  Location.prototype

window의 location이라는 property가 가진 값
앞에 f붙은것은 method
그냥 기본값은 property
 
why use prototype?
location 객체가 여러개 있을때 method들이 중복되지 않도록 부모역할 객체한테 주면 다 같이 상속받고 중복을 막고 메모리를 절약할 수 있어서.


### DOM
- Document Object Model is an API that represents and interacts with any HTML or XML document.


### Standard Built-in Object (native object : BOM , DOM  를 제외한)
- what is 전역객체 : window (frontend 개념)  | global (node js에서는 global이 전역)
- window 내에는 native object가 들어있다.
- back-end node js 에서는 native 가 필요없다.
- 모든 객체의 최상위 객체 

---
Window
- property
- isFinite() - is ? boolean 

---
### string

문자열은 크기가 정해져 있다 - 내부적으로는 stack에 저장되지 않고 heap 에서 관리한다.
기본자료형으로 정해놓은 이유는? 사용빈도가 높기 때문에.
유사배열객체 : 객체인데 배열과 비슷한 객체이다 -> 순회할 수 있다. 순서가 있다 -> for문으로 돌릴 수 있다.




