## CALC()

`calc()` function allows methematical expressions with `+, -, *, /` to be used as component values.


- Calc is especially useful when calculating relative widths.
- `cal()` can mix any kiund of units.
- use whitespace around operators so that they aren't contrued as positive and negative notations.



```css
//width of box is always 100px smaller than parent element.
.box{
    width: calc(100% - 100px);
}
```

---

```css
.moreBox{
    width: calc(100% - 50% / 3);
    padding: 5px calc(3% - 2px);
    margin-left: calc(10% + 10px);
}
```

---

```css
//this example stacks two centered background images, with one offset slightly from the other.

.foo{
    background: url(top.png), url(bottom.png);
    backgorund-repeat: no-repeat;
    background-position: calc(50% + 20px) calc(50% + 20px), 50% 50%;
}
```

```css
//this example show how to place color-stops on a gradient an equal distance from either end.

.foo {
    background-image: linear-gradient(to right, silver,
                                                white 50px,
                                                white calc(100% - 50px),
                                                silver);
}

```