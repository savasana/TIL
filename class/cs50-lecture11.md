# CS50 Lecture11
>Harvard CS50 Lecture11
---
## MVC
- Model View Controller
- software architectural design pattern
- separates application functionality
- Ruby on Rails, Express, Angular, Django, Flask, 


## Javascript

```html
<html>
<head>
</head>
<body>
	<form id="demo">
		<input autocomplete="off" autofocus id="demo" placeholder="Name" type="text">
		<input type="submit" />
	</form>
	<script>
		funtcion greet(){
			alert("hello world!");
		}
	
		document.getElementById("demo").onsubmit = greet;
	</script>
</body>
</html>

```

`document.getElementById("demo").onsubmit = greet;`

why omit the `()` after `greet`?
Because you would want to avoid calling the function right at that line. The computer will automatically call the function if it sees `()` after whatever function that is.


```js
document.getElementById(“demo”).onsubmit = function(){
	alert("hello world");
}
```

Function without name is called anonymous function.  The parenthesis  `()` after the function is followed by the curly brace `{`, which tells the computer that  it’s a **call back** function.




### Google Maps 
If you move around your mouse on the screen, delay happens. (gray grid appears)
why delay? it request informations in a real short amount of time (and it is called AJAX)

**needed to comeback for more info here**


### JSON


### Callback
“Get back to me when you have the data the I requested!”


### Asynchronous code

**synchronous code**
- `C` is synchronous code  
- works line by line , it means if one line takes a while it's going to just hang there til it’s over.

**asynchronous code**
- `Javascript`  `flask` is asynchronous code 
- it registers all of those code and waits things to happen asynchronously. 
- do more things at once
- callback - ex) web geolocation  


