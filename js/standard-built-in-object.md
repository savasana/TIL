### Standard Built-in Object

> The term "global objects" (standard built-in objects) is not to be confused with the **global object**. Here, global objects refer to **objects in the global scope**.
> [MDN : Standard Built-in Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)

- 전역에서 공통적으로 필요한 기능을 제공하는 Standard Built-in Objects가 있다.
- Object, Function, Boolean, Number, Math, String, RegExp, Array, Error..
- 자체 method와 prototype method가 있으니 MDN에서 잘 숙지하고 사용할것.


**Boolean, Number,String은 primitive value인 boolean, number, string과 구별해야 한다. Boolean, Number, String은 기본자료형을 다룰 때 유용한 메소드등을 제공하는 wrapper객체이다. 호출할때 기본자료형은 연관된 wrapper객체로 일시적 형변환이 일어난다.(다시 원래 type으로 변환 후 반환)**


---

### Number

- Number Object는 기본자료형 number다룰 때 유용한 프로퍼티와 메소드를 제공하는 wrapper object이다
- new 연산자를 붙이지 않고 사용하면 기본자료형 숫자를 반환한다. can be used to perform a type conversion.

---

#### Number.isFinite(value)

- return : A `Boolean` indicating whether or not the given value is a finite number.
- `window.isFinite()` : forcibly convert the parameter to a number
- `Number.isFinite()` : only values of the type number, that are also finite, return true

```js
  Number.isFinite('123') // false
  isFinite('123') // true
```

---

#### Number.isInteger()

- Number.isInteger(num)
- return : A `Boolean` indicating whether or not the given value is an integer

```js
Number.isInteger(0.1);       // false
Number.isInteger(Math.PI);   // false
Number.isInteger(NaN);       // false
Number.isInteger(Infinity);  // false
Number.isInteger(-Infinity); // false
Number.isInteger('10');      // false
Number.isInteger(true);      // false
Number.isInteger(false);     // false
Number.isInteger([1]);       // false
```
---

#### Number.isNaN()

- determines whether the passed value is `NaN` and its type is Number.
- window.isNaN() 보다 엄격하게 NaN타입을 확인 할 수 있다.

```js
//window.isNaN
isNaN(NaN)          // false
isNaN('NaN')        // true?
isNaN(undefined)    // true???

Number.isNaN(NaN)   // true
Number.isNaN('NaN') // false
Number.isNaN(undefined) //false
Number.isNaN('37')  //false
```

---

#### Number.prototype.toFixed()

- formats a number using fixed-point notation (반올림한다!)
- `numObj.toFixed(digits)`
- digits : The number of digits to appear after the decimal points(0 - 20), optional (if omitted - 0)
- return : string 

---

#### Number.prototype.toPrecision()

- 매개변수로 지정된 전체 자릿수까지 유효하도록 나머지 자릿수를 반올림하여 문자열로 반환
- `numObj.toPrecision(precision)`

```js
var numObj = 5.123456;

console.log(numObj.toPrecision());    // logs '5.123456'
console.log(numObj.toPrecision(5));   // logs '5.1235'
console.log(numObj.toPrecision(1));   // logs '5'

numObj = 0.000123

console.log(numObj.toPrecision());    // logs '0.000123'
console.log(numObj.toPrecision(5));   // logs '0.00012300'
console.log(numObj.toPrecision(2));   // logs '0.00012'
```

---

#### Number.prototype.toString()

- returns a string representing the specified Number object
- `numObj.toString(radix)` : radix 진수, 옵션, 2 ~ 36

---

### Math

- `Math` is not a constructor (new Math 성립하지 않아)
- All properties and methods of `Math` are **static**

- `Math.abs(-1)`      // 1   절대값 반환
- `Math.round(20.5)`  // 21  인접한 정수로 올림 혹은 내림해서 반환
- `Math.sqrt(9)`      // 3   *양*의 제곱근 반환
- `Math.ceil(1.4)`    // 2   지정된 숫자를 자신보다 큰, 가장 가까운 정수로 올림 반환
- `Math.floor(1.9)`   // 1   자신보다 작은, 가장 가까운 정수로 내림 반환
- `Math.random()`            0 ~ 1 미만의 소수 반환 
- `Math.pow(7, 2)`    // 49  7을 base로 2를 exponent로 계산후 반환
- `Math.max(1,2,3)`   // 3   
- `Math.min(1,2,3)`   // 1


```js
// 1부터 maxNum까지(1과 maxNum포함) 랜점 정수 뽑기
function getRandomInt(maxNum) {
  return Math.floor((Math.random() * maxNum) + 1)
}
```


```js

console.log(Math.max(1,2,3)); // 3

var arr = [1,2,3,4,5];
console.log(Math.max(...arr));  // 5 ES6!!

//ES5에서는 apply를 사용해서
var arr = [1,2,3,4,5];
Math.max.apply(null,arr);   //5

```


---


### String

- [MDN : String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- new 연산자 사용하지 않고 호출하면 문자형으로 반환
- array-like object로 인덱스를 가지고 순회할 수 있다


> JavaScript automatically converts primitives to String objects, so that it's possible to use String object methods for primitive strings. In contexts where a method is to be invoked on a primitive string or a property lookup occurs, JavaScript will automatically wrap the string primitive and call the method or perform the property lookup.


---



#### String.prototype.length

- property (not a method - no invokation)
- returns the number (the length of a string)
- static property인 `String.length`와 주의할것 (항상 리턴1)

```js
'hello'.length; //5
```

---

#### String.prototype.charAt()

- return: a **new string** consisting of the single code unit located at the specified offset into the string.
- `character = str.charAt(index)`

```js
var str = 'Hi';

console.log(str.charAt(0)); // H
console.log(str.charAt(1)); // i

```

---

#### String.prototype.indexOf()

- `str.indexOf(value[, fromIndex])`: [~]는 옵션값을 나타냄
- return: the index of the first occurence of `value`
- 찾지 못했을 때는 `-1` 반환한다  
- 대소문자 구분
- `String.prototype.lastIndexOf()` 마지막으로 발견된 곳 index 반환


```js
// 특정 알파벳 갯수 새기
var str = 'the secret of getting ahead is getting started';
var count = 0;
var position = str.indexOf('e');

while (position !== -1) {
  count++;
  position = str.indexOf('e', position + 1);
}

console.log(count);
```

---

#### String.prototype.replace()

- `str.replace(regexp|substr, newSubstr|function)`
- return: **new string** with some or all matches of a `pattern` replaced by a `replacement`.
- `pattern` can be a string or a `RegExp`
- `replacement` can be a string or a function to be called for each match

```js
var str = 'we wish you a merry xmas';
var newStr = str.replace(/xmas/i, 'Christmas');
console.log(newStr);  // "we wish you a merry Christmas"
```


---

#### String.prototype.split()

- `str.split([seperator[, limit])`
- splits a string object into an array of strings by separating the string into substrings, using a specified separator string to determine where to make each split.
- `separator` is optional.
- `limit`
- return: an array of strings


```js

var str = 'hello world. how are you doing?';
var splitStr = str.split(' ', 3);   //["hello", "world.", "how"]
var splitStr = str.split(' ');      // ["hello", "world.", "how", "are", "you", "doing?"]
var splitStr = str.split('o');      //["hell", " w", "rld. h", "w are y", "u d", "ing?"]
//'o'으로 구분하여 배열을 반환

```


```js
//reversing words order
var str = 'dahye oh';
var newStr = str.split(' ').reverse().join(''); //"oh dahye"

//reversing a string 
var str = 'yohansong';
var newStr = str.split('').reverse().join('');  //"gnosnahoy"

```

---


#### String.prototype.substring()

- `str.substring(indexStart[, indexEnd])`
- indexStart: 0 ~ length of the string
- return: a **new string** containing the extracted section of the given string

```js
var num = '01038083082';
var newNum = num.substring(num.length-4); // "3082"
```
---

#### String.prototype.substr()

- `str.substr(start[, length])`
- `substring()`과 헷갈리지 말것
- start point부터 길이

```js
var text = 'Mozilla';
console.log(text.substring(2,5)); // => "zil"
console.log(text.substr(2,3)); // => "zil"
```

---
