# Array

#### Array.prototype.concat()

- 두개 이상의 배열(일수도 있고 아닐수도 있음)을 합친다. (값으로 합친다)
- 인자(arguments)는 배열일 수도 있고 값일 수도 있다
- 새로운 배열을 반환함, 원본배열은 변경되지 않는다.

```js
var array1 = ['a', 'b', 'c'];
var array2 = ['d', 'e', 'f'];

console.log(array1.concat(array2));
// expected output: Array ["a", "b", "c", "d", "e", "f"]

```

---

#### Array.prototype.push()

- **원본배열 변경**
- 배열의 마지막 인덱스에 argument값을 추가
- 배열의 새로운 길이값을 반환한다 (new length)
- 배열을 push 하면 배열이 배열에 추가된다. `[a, b, [c, d]]`


#### Array.prototype.pop()

- **원본배열 변경**
- `push`와 반대로 배열의 마지막 요소를 뺀다(리턴)

#### Array.prototype.shift() / Array.prototype.unshift() 
- 비슷한데 앞에서 부터

---

#### Array.prototype.join([seperator])

- 연결된 **문자열** 반환
- separator안주면 ,(comma)로 연결 

```js
var elements = ['Fire', 'Wind', 'Rain'];

console.log(elements.join());
// expected output: Fire,Wind,Rain

console.log(elements.join(''));
// expected output: FireWindRain

console.log(elements.join('-'));
// expected output: Fire-Wind-Rain
```

---

#### Array.prototype.reverse()

- **원본배열 변경**
- 배열 요소 순서를 반대로 변경

```js
var a = ['one', 'two', 'three'];
var reversed = a.reverse(); 

console.log(a);        // ['three', 'two', 'one']
console.log(reversed); // ['three', 'two', 'one']
```

---

#### Array.prototype.slice([begin,[ end]])

- begin부터 end 전까지(end는 미포함)
- 새로운 배열을 반환
- 음수를 쓰면 뒤에서 부터 ..
- 유사배열을 배열로 바꿀때 사용한다. `Array.prototype.slice.apply(~)`
- 인자요소가 없으면 배열을 copy한다.  `array.slice()`

---

#### Array.prototype.splice(start[, deleteCount [, item1 …]])

- **원본배열 변경**
- start부터 deleteCount갯수 만큼 제거하고 제거된 요소를 배열로 반환
- item1 …은 제거하고 추가할 요소를 줄 수 있다
- deleteCount에 0을 주면 제거안하고 그 자리에 추가할 수 있다.

```js
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2, 0, 'drum');

// myFish is ["angel", "clown", "drum", "mandarin", "sturgeon"] 
// removed is [], no elements removed
```

- 배열 중간에 새로운 배열을 추가할 때 
```js
var items = ['one', 'four'];
Array.prototype.splice.apply(items, [1, 0].concat(['two', 'three']);
								// 1에 자리에 추가해라 'two' 'three'를
// items = [ 'one', 'two', 'three', 'four' ]
```

---

#### Array.prototype.sort(compareFunc)

- 인자를 안주면 오름차순으로 정렬 (숫자 제대로 동작하지 않음)


---

#### Array.prototype.forEach(callbackFunc[, thisArg])

- 배열에서 사용할 수 있는 for문 (내부적으로는 for문에 돌고있음)
- 각 요소에 대하여 인자로 주어진 콜백함수를 실행한다.
- 콜백 함수는  **item, index, array** -3개의 인자가 들어올 수 있다. (네이밍 무관)
- 원본배열은 변경하지 않는다
- break 쓸 수 없다.

```js
var testArray = [1, 3, 5, 7, 9];

// forEach 메소드는 원본 배열을 변경하지 않는다.
testArray.forEach(function (item, index, array) {
  console.log('[' + index + '] = ' + item);
});
// item 은 1, 3, 5, 7, 9
// index는 0, 1, 2, 3, 4
```

- `thisArg`

```js
function Counter() {
  this.sum = 0;
  this.count = 0;
}
Counter.prototype.add = function(array) {
  array.forEach(function(entry) {
    this.sum += entry;
    ++this.count;
  }, this);
  // ^---- Note
};

const obj = new Counter();
obj.add([2, 5, 9]);
obj.count;
// 3 
obj.sum;
// 16
```

---

#### Array.prototype.map( callback(item, index, arr), thisArg )

- 로직을 수행한 결과값을 새로운 배열로 반환한다. (`forEach`는 로직만 수행)
- 원본 배열과 길이가 같음
- `forEach`와 마찬가지로 2개의 매개변수와 콜백함수 내에 3개의 매개변수
- **return** 반드시 존재해야 함 (`forEach`는 return 필요없음)

---

#### Array.prototype.filter( callback(item, index, arr), thisArg )

- 순회하면서 콜백함수의 실행결과(return) 가 true인 요소 값만 추출하여 새로운 배열 반환


---

#### Array.prototype.reduce( callback(accumulator, currentValue, currentIndex, array), initialValue )



---
#### Array.prototype.some(  callbackFunc )

- 하나라도 truth value 이면 true, 아니면  false


---
#### Array.prototype.every()

- 모든 요소가 콜백함수의 테스트를 통과하는지 그 결과를 boolean으로 반환
- 모든 요소에 대해서 truths value일때 true , 하나라도 아니면 false

---
#### Array.prototype.find()

- 배열을 순회하며 각 요소에 대하여 인자로 주어진 콜백함수를 실행하여 그 결과가 참인 첫번째 요소를 반환한다.
- `filter`는 배열을 반환하고 `find`는 요소를 반환한다

