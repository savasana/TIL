## Functional Programming

### Imperative vs Declarative

- Imperative : 명령적인, 
- Declarative : 선언하는, 서술적인
- imperative는 컴퓨터가 이해하기 쉽지만 인간이 이해하기 어렵다.
- Declarative 가 인간이 이해하기 쉽기 때문에 많이 쓰고 있다. 
- perception of readability problem
- abstraction is not about encapsulating or hiding / creating symactic boundaries.



---



### Function



- collection of operation (percedures) and functions are different thigs
- function needs `return` value
- needs direct input, direct output (not side effect)
- why no side effect?  함수만 봐서는 어떤 결과가 나올지 예측할 수 없다. (이미 앞에서 변했는지 알 수 없음.)
- avoid side effect!



```js
function foo(x,y) {
    return [x+1, y-1];
}
```



```js
function f(x) {
    return 2 * Math.pow(x,2) + 3;
}

var y;
y = f(0); 	//3
y = f(2);	//11
y = f(-1);	//5

// direct input and output!
```



### Pure Function

- with no side effect
- ​