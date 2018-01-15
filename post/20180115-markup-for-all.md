## The importance of meaninfulness in Web
의미있는 이름짓기의 중요성(네이밍&마크업)

> There are only two hard problems in Computer Science: cache invalidation and naming things — Phil Karlton


## Web technologies for all
Accessibility & Web Standards = BETTER WORLD
웹표준과 접근성 그리고 호환성을 더 나은 세계를 향한 첫걸음.

## Don't just use <div>
Be careful when using **div**. Div has no actual semantic meaning itself so use it when no other option is available or when grouping others (like wrapper).
<div>는 그 자체로는 의미가 없이 중립적인 요소이다. 따라서 남발하기 보다는 다른 요소로 표현이 안되는 경우, 혹은 다른부분들을 한번에 묶어줘야하는 경우(wrapper)에 사용하도록 하자.

```html
	<div>
    <div>this is header title</div>
    <div>main contents</div>
	</div>
```
This is a bad example - just using divs, computer can’t find meaning and its bad for acceesability.


```html
	<div class="wrapper">
		<header class="header">header title</header>
		<main class="main-content">main contents</main>
	</div>
```
This is the better solution. Use  `<header>`  for header and `<main>` for the main content.

## Markup first , design later
html을 구조를 짤때는, 보이는 디자인 중심으로 생각하지말고 컨텐츠중심으로 **논리적**으로 접근하자. `header`가 디자인상 아래에 위치하더라도 절대! 아래로 짜면 meaning이 엉망이 되버린다. 베리베리 스튜핏!

## Check your validation often
When writing HTML or CSS, check your file’s validity as often as possible. 
- For HTML Validation - [The W3C Markup Validation Service](http://validator.w3.org/#validate_by_upload) 
- For CSS Validation - [The W3C CSS Validation Service](http://jigsaw.w3.org/css-validator/)

## BEM Method

**BEM (Block, Element, Modifier)** is a component-based approach to web development. The idea behind it is to divide the user interface into independent blocks. This makes interface development easy and fast even with a complex UI, and it allows reuse of existing code without copying and pasting.

#### related links
- [BEM Method](https://en.bem.info/methodology/quick-start/)
- [getBem.com](http://getbem.com/naming/)