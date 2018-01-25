## Pseudo Element’s contents

### ::before , ::after
`content: counter(name,style);`

```css

li{
	counter-increment: number;
}

li::before{
	content: counter(number, decimal);
}

```

### result would be like
1. something something
2. something something
3. something something ...

**easy to style than `list-style` element.**

`counter` can be useful when you have ranked items.
The value of a CSS counter, generally a number. It can be displayed using the `counter()`  function.


The counter() function has two forms: `counter(name)` or `counter(name, style)`. The generated text is the value of the innermost counter of the given name in scope at the given pseudo-element. It is formatted in the specified style (`decimal` by default).


