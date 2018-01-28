## You Don’t Know JS : Up & Going 


`.` object property access
 `obj.a`  -> object value called `obj` with a property of the name `a` Properties can alternatively be accessed as `obj["a"]`

---
### Comments

Code without comments is suboptimal.
Too many comments is probably a sign of poorly written code.
Comments should explain **why, not what.**

---
### Variables

- The primary purpose of variables: managing program state. State is tracking the changes to values as your program runs.
- To centralizing value setting.(constants) when you declare a variable with a value and intend for that value to not change throughout the program.
- By convention, variables as constants are usually capitalized, with underscores between multiple words. `const  TAX_RATE = 0.08;`


---
### Block

- A block is defined by wrapping one or more statements inside a curly-brace pare `{ something something }`
- A block statement does not need a semicolon `;` go conclude it.

---

### Conditionals

`if( amount < bank_balance ) { do this }`

Values that aren’t already of an expected type are often coerced to that type. The `if` statement expects a `boolean:true or false`, but if you pass it something that’s not already boolean , coercion will occur.
False values - `0` `""`. Any other value not on the false list is automatically truthy values.


---

### Loops

`while` / `do..while`/ `for`


---

## Programming building blocks
- You need **operators** to perform actions on values.
- You need values and **types** to perform different kinds of actions like math on numbers or output with strings.
- You need conditionals like `if` statements to make decisions.
- You need **loops** to repeat tasks until a condition stops being true.
- You need **functions** to organize your code into logical and reusable *chunks.*

**The best way to learn how to write code is to write code**

----
## Object



## Array
The best and most natural approach is to use arrays for numerically positioned values and use objects for named properties.


---

### Equality

`==` checks for value equality with coercion allowed
`===` checks for value equality without allowing coercion, strict equality

- If either value (aka side) in a comparison could be the true or false value, avoid `==` and use `===`.
- If either value in a comparison could be of these specific values (0, "", or [] -- empty array), avoid `==` and use `===`.
- In all other cases, you're safe to use `==`. Not only is it safe, but in many cases it simplifies your code in a way that improves readability.

#### non-equality

`!=` pairs with `==`
`!==` pairs with `===`


#### Inequality
`< , > , <= , >=` relational comparison.
**no “strict inequality” forms!!**

```js
var a = 31;
var b = "32";
var c = "35";

a < b; //true
b < c; //true
```

```js
var a = 41;
var b = "100";
var c = "42";
a < b; //true
b < c; //true 
//both strings -> comparison is made lexicographically (alphabetically)
```

If both values in the `<, >`comparison are `string`, the comparison is made lexicographically (alphabetically). But if one or both is not a `string` , then both values are coerced to be `number`

```js
var a = 42;
var b = "foo";

a < b;		// false
a > b;		// false
a == b;		// false

// b value is coerced to the `NaN` (invalid number value)
```

---

### Scope


#### Hoisting
(hoist : raide, lift, haul up, pull up)


```js
var a = 2;
foo(); 		//works because foo function is hoisted


function foo() {
	a = 3;
	console.log( a );
}

```


---
### Conditionals

```js
switch (a) {
	case 2:	//do something
			break;
	case 10: //do this
			break;

	default:
			//fallback to here
}
```


`break` is important if you want only the statement in one case to run. If you omit `break` from a case,  the execution will continue with the next case’s statements. This is called **fall through**.


**ternary operator**
`var a = 42; `
`var b = ( a > 41 ) ?  “hello” : “world”;`

if `a > 41` is truth do `“hello”` else do `"world"`


---

### Strict Mode

Not only will strict mode keep your code to a safer path, and not only will it make your code more optimizable, but it also represents the future direction on the language. 

```js
"use strict";

function foo() {
	// this code is strict mode

	function bar() {
		// this code is strict mode
	}
}

// this code is strict mode

```


---

### Functions as values

Not only can you pass a value(argument) to a function, but a function itself can be a value that’s assigned to variables, or passed to or return from other functions.

```js
var foo = function() { //.. };
//function expression assigned to the foo variable.
// anonymous function

var x = function bar() {	//.. };
//function expression is named bar, even as a reference to it is also assigned to the x variable.
```


#### IIFE ( Immediately Invoked Function Expressions)


---

### Closure and Modules

```js
function User(){
	var username, password;

	function doLogin(user,pw) {
		username = user;
		password = pw;

		// do the rest of the login work
	}

	var publicAPI = {
		login: doLogin
	};

	return publicAPI;
}

// create a `User` module instance
var fred = User();

fred.login( "fred", "12Battery34!" );

```

---

### `this`

the `this` keyword is dynamically bound based on how the function in question is executed.
```js
function foo() {
	console.log( this.bar );
}

var bar = "global";

var obj1 = {
	bar: "obj1",
	foo: foo
};

var obj2 = {
	bar: "obj2"
};

// --------

foo();				// 1. "global"
obj1.foo();			// 2. "obj1"
foo.call( obj2 );		// 3. "obj2"
new foo();			// 4. undefined


```


---

### prototypes

When you reference a property on an object, if that property doesn’t exist, JavaScript will automatically use that object’s internal prototype reference to find another object  to look for the property on.
You could think of this almost as a fallback if the property is missing.


---

### Polyfilling & Transpilling

---



