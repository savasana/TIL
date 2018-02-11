## Execution Context


자바스크립트에서 코드가 실행되어지는 환경이 굉장히 중요하다. 이 환경은 아래중 한개로 결정된다.

- Global code : 기본 환경으로 가장 처음 코드가 실행되는 곳이다.
- Function code : 실행 흐름이 함수의 몸체로 들어오면 실행되는 곳이다.
- Eval code : eval 함수 실행시 환경

---

### `global context` and `function contexts`

- 프로그램 내에 하나의 global context를 가진다.
- global context는 다른 컨텍스트들에 의해 접근가능하다.
- 무제한의 `function contexts`를 가질 수 있다.
- 각각의 함수 호출은 각각의 새로운 컨텍스트를 형성한다.
- `function contexts`는 프라이빗 스코프를 형성한다. 



### Execution Context Stack

브라우저 내의 자바스크립트 인터프리터는 싱글스레드 방식으로 실행된다. 브라우저에서는 한번에 한가지 일만 일어날 수 있고, 이때 실행되는 컨텍스트는 `execution stack`, `call stack`에 쌓여서 위에서부터 순차적으로 진행된다.

가장 먼저 브라우저가 스크립트를 가져오면, 기본 환경 값인 `global execution context` 환경으로 들어간다. 

이 안에서 함수를 호출하면 실행의 흐름은 함수로 들어가게되고 이때 stack에 `function context`가 `global execution context`위로 push되어 쌓인다. 브라우저는 항상 스택의 가장 위에 쌓인 현재의 `execution context`를 실행하고, 실행이 끝나면 그 `execution context`는 stack에서 popped off(빠져나가게)되고 아래 위치한 context로 실행이 옮겨간다. 

![콜스택이미지](./images/call-stack.png)

---

`execution context stack`의 특징은 다음과 같이 정리할 수 있다.

- Single threaded
- Synchronous Execution
- One Global context
- Infinite function contexts
- each function call creates a new `execution context`


함수가 호출될 때마다 새로운 `execution context`가 생성되는데 이때 2단계를 거친다.

1. Creation Stage - 호출되고 실행 직전에
  - Scope Chain을 생성한다
  - variables, functions, arguments를 생성한다
  - 'this' 가 가리키는 값을 결정한다

2. Activation / Code Execution Stage 
  - 값 또는 참조값을 할당한다.
  - 코드를 실행한다


---


### Call stack

> A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run, what functions are called from within that function and should be called next, etc.

- When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
- Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
- When the main function is finished, the interpreter takes it off the stack and resumes execution it left off in the main code listing.
- If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.

> from MDN
 
---

크롬 브라우저 환경에서 볼 수 있는 자바스크립트 엔진은 단일의 'call stack'으로 이루어진 single-threaded interpreter이다.- 여기서 'Thread'(스레드)란, 프로그래밍이 실행되는 흐름의 단위를 말한다. 하나의 thread를 가지고 한번에 하나씩 실행하는 경우를 single thread, 여러개를 동시에 실행할 수 있으면 multithread라고 한다.

콜스택에 대한 이해가 함수의 위계와 실행 순서의 동작 방식을 이해하는데 큰 도움이 될 것이다. 콜스택은 주로 함수호출(call)을 위해 사용되며 하나만 존재하기 때문에 한번에 하나의 테스크(task)를 위에서 아래로 진행된다. -콜스택은 synchronous 라고 할 수 있다.

콜스택은 함수의 호출을 임시로 저장하고 관리하기 위한 LIFO방식의 데이터 구조이다. 

---

에러를 던져 콜스택이 어떻게 구성되는지 볼 수 있다.

```js
function firstFunction(){
throw new Error('Stack Trace Error');
}
function secondFunction(){
firstFunction();
}
function thirdFunction(){
secondFunction();
}
thirdFunction();
```

---


크롬 콘솔로 찍어보면 다음과 같이 나온다.
콜스택이 `firstFunction()` -> `secondFunction()` -> `thirdFunction()` 순으로 되있을 걸 볼 수 있다.

![콜스택이미지](./images/callstack.png)

---
**참고링크**

- [Understanding Javascript Function Executions](https://medium.com/@gaurav.pandvia/understanding-javascript-function-executions-tasks-event-loop-call-stack-more-part-1-5683dea1f5ec)
- [Understanding the JavaScript call stack](https://medium.freecodecamp.org/understanding-the-javascript-call-stack-861e41ae61d4)

---
