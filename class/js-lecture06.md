### Number 


number는 기본 자료형인데 wrappe가 객체 처럼 사용 할 수 있게 도와준다.
Number.protype의 method를 가져다 쓸 수 있다.

일급객체 


---
window.isFinite()
Number.isFinite() : 더 엄격하다


---

### Math

Math.max(1,2,3);
arguments들 중에서 가장 큰 순


---

### apply

Math.max.apply();

- apply : 호출할때 this를 정해줄 수 있다.(안줘도 됨)

---


### Regular Expression

#### 정규표현식

 - 문자열에서 특정 내용을 찾거나 대체 또는 발췌하는데 사용
 - 대부분의 컴퓨터 언어는 정규표현식을 지원한다.
 

`var myRegExp = /^[0-9]+$/;`

`/regexr/i`
`/` : 시작과 종료
`regexr` : 패턴
`i` : ignore 대소문자 구분 안한다

---
`console.log(regexr.exec(targetStr));`
`// [ 'is', index: 2, input: 'This is a pen.' ]`

`console.log(regexr.test(targetStr));`
-> true / false

---

`String.prototype.replace( a, 'replacement')`
a 에는 string도 가능하고 정규표현식도 가능하다.
일반 string을 쓰면 무조건 한개만 찾는데 정규표현식을 쓰면 다 찾아줌.

replace는 주로 정규표현식을 사용
split은 그냥 사용해도 편함...

---

`/./` 임의의 문자 (쩜 갯수에 따라) - 앞에서부터 n개

```js
var targetStr = 'AA BB Aa Bb';
// 임의의 한문자를 반복 검색
var regexr = /./g;
console.log(targetStr.match(regexr));
```

`targetStr.split('')` 과 동일

---

`/a/` a를 찾아라 no flag 대소문자 구문, 한개만
`/a/ig`  대소문자 구문없이 모든 a를 찾아라
`/a+/g` 한번이상 연속된 a를 모두 찾아라 (a한개이상)
`/a|b/g;` a또는 b를 전부 찾아라
`/[ab]+/g`


---

### Array 배열

데이터 왔다갔다 하려면 문자열화 되어야하고
효율적이기 위해서 최소한의 데이터로. 
-> JSON은 배열 형식으로 되어 있다.
따라서 array 중요

-> 배열을 통해서 html을 만든다.


---
### 배열 생성

- 리터럴 사용
- 배열의 요소 
- 순서를 가지고 있다 index 0, 1, 2, ...
- 순회할 수 있고 순서가 보장된다.
- iterate 
- Array.prototype.map()
- Array.prototype.filter()
- Array.prototype.forEach()
- Array.prototype.

- 고차함수?

---

원본을 건들이는 (값을 직접 변경하는) method가 있고 그렇지 않은 애들이 있다.
Array.prototype.push(‘~) // array를 직접 바꾼다. 
Array.prototype.concat() // 합친 배열을 새로 반환한다.









