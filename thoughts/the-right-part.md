### es6 the right parts


### rest operator(gather operator)

- gathers or spreads
- `...` assignment context(argument -> parameter, var x = y) 사용될 때는 gathers
- 위의 경우 아닐 때 (list context) 일때는 spread
- iterable values(array, string,...) can use ... spread operator


```js
// es5
var a = "hello";
var arr = [].slice.call(a);
// arr -> ["h", "e", "l", "l", "o"]
```


```js
// es6
function foo( ...arg ) { //gather to array
    args.unshift( 42 );
    bar( ...args ); //spread args
} 
```

```js
var x = [1, 2, 3];
var y = [4, 5];

// var z = [0].concat(x, y, [6]);
var z = [0, ...x, ...y, 6];
// [0, 1, 2, 3, 4, 5, 6]
```

```js 
function foo(x, y, ...rest) {
  // x = 1, y = 2, rest = 3, 4, 5
  return rest; 
}
foo( ...x, ...y); // spread => foo( 1, 2, 3, 4, 5 )
// [3, 4, 5]
```

**exercise**

```js
function ignore23(x, y, z, ...rest) {
	return [ x, ...rest];
}

function bar() {
	var a1 = [ 2, 4 ];
	var a2 = [ 6, 8, 10, 12 ];

	return ignore23( ...a1, ...a2 );
}

console.log(
	bar().join("") === "281012"
);
```

---

### Destructuring

- array destructuring

```js
function foo() {
  return [1, 2, 3];
}

var tmp = foo();

// es5
var a = tmp[0];
var b = tmp[1];
var c = tmp[2]
// es6
var [a, b, c] = foo();
// a = 1;
// b = 2;
// c = 3;
```

- for swaping values

```js
var x = 10, y = 20;
[x, y] = [y, x];
// x = 20;
// y = 10;
```

- dumping variables

```js
var a = [1, 2, 3];
[ , , ...a ] = [ 0, ...a, 4 ];
// lhs ...Gather  = rhs ...Spread
// 앞에 두 값은 버리고 나머지만 a로
// a = [2, 3, 4]
```

### Concise properties and methods

```js
var a = 1;
var obj = {
  a,
  b() {};
  // b = function() {} lexically anonymous function
}
```

- commuted properties

```js
var a = 1;
var c = "hello";
var obj = {
  a,
  [c]: 32
  };
obj.hello;
// 32
```

---

### Template Strings

```js
var name = "Kyle";
var orderNumber = "123";
var total = 319.7;

var msg = `Hi, ${name}, your order (#${orderNumber}) was $${total}.`;

// multi line 
var msg = `Hi, ${name}, your 
order (#${orderNumber}) was $${total}.`;
// "Hi, Kyle, your
//order ~~~~ ."

// single line - use back slash
var msg = `Hi, ${name}, your order \
(#${orderNumber}) was $${total}.`;
// "Hi, Kyle, your order (#123) was $319.7."

```


### Symbol.iterator

- iterator
- `for..of`  loop, which loops over the set of values produced by an iterator. The value you loop over with  for..of  must be an iterable, or it must be a value``

```js
for (var val of a) {
  console.log( val ); 
} // "a" "b" "c" "d" "e"
```