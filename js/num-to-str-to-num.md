## number to string, string to number

자바스크립트에는 타입을 변경시키는 다양한 방법들이 있다.

숫자를 문자로, 문자를 숫자로 바꾸는 여러가지 방법들을 알아보자



#### convert a string to a number

- `num = Number(str)`    // Number 생성자 사용
- `num = parseInt(str)`  // base에만 사용할것을 권장
- `num = +str`          // unary operators 가장 간편
- `num = str / 1`
- `num = str * 1`

이외에도 parseInt에 진수를 지정해 주는 방법, parseFloat을 쓰는 방법도 발견했는데 unary operator 가장 편리해 보인다.
각각 방법들 마다 속도가 다르다고 사람들이 뭐가 더 빠른지 두고 논쟁?이 많은데 나는 아직까지는 + 로 만족한다.


#### convert a number to a string

- `str = num.toString();`   // null, undefined일때는 제대로 작동하지 않는다
- `str = String(num)`       // 그다지 추천하지 않는다 (by 쌤)
- `str = num + '';`         // 빈 스트링 더해준다 - 가장 간편

위의 경우와 마찬가지로 + 를 사용해서 빈 스트링을 더해주는게 가장 쉽고 빠르게 바꿀 수 있는거 같다. 

---

### bonus study

`+`의 경우 위처럼 Unary operator로 사용할 수 있고 아래의 경우처럼 Arithmetic Operators의 add의 의미로 사용 가능하다. Unary Operators와 Arithmetic Operators에 대해 잠시 알아보자.

---


#### Unary plus `+`

> The unary plus operator precedes its operand and evaluates to its operand but attempts to convert it into a number, if it isn't already. Although unary negation (-) also can convert non-numbers, unary plus is the fastest and preferred way of converting something into a number, because it does not perform any other operations on the number. It can convert string representations of integers and floats, as well as the non-string values true, false, and null. Integers in both decimal and hexadecimal ("0x"-prefixed) formats are supported. Negative numbers are supported (though not for hex). If it cannot parse a particular value, it will evaluate to NaN.

unary + 는 값을 숫자고 바꾸려고 한다. 다른 값을 숫자로 바꾸는데 가장 빠른 방법 중 하나이다. unary +는 숫자에 어떠한 작업을 하지 않기 때문이다...라고 MDN에 명시되어 있다. 바꾸는데 실패하면  NaN.


```js
+3     // 3
+'3'   // 3
+true  // 1
+false // 0
+null  // 0
+function(val){  return val } // NaN
```

---


#### Arithmetic Operators

> Arithmetic operators take numerical values (either literals or variables) as their operands and return a single numerical value. The standard arithmetic operators are addition (+), subtraction (-), multiplication (*), and division (/).

- 수로 표시되는 값들을 연산해 하나의 숫자값으로 반환한다. 기본적으로 `+`, `-`, `*`, `/` 이 있다.


#### Addition `+`
- The addition operator produces the sum of numeric operands or string concatenation.
- 숫자의 합 또는 문자의 합을 나타낸다. **자동 형변환이 일어남에 주의할것** ( = 잘 알아두고 활용할것)

```js
// Number + Number -> addition
1 + 2 // 3
// Boolean + Number -> addition
true + 1 // 2
// Boolean + Boolean -> addition
false + false // 0
// Number + String -> concatenation
5 + 'foo' // "5foo"
// String + Boolean -> concatenation
'foo' + false // "foofalse"
// String + String -> concatenation
'foo' + 'bar' // "foobar"
```