## what is the CSS Box Model

HTML의 요소들은 하나의 박스라고 생각할 수 있다. CSS에서는 전체적인 디자인과 레이아웃을 고려할 때 "box model"이라는 용어를 사용한다. CSS box model은 html요소를 감싸는 박스로, margin, border, padding 그리고 실제 컨텐츠로 이루어져 있다.

**Basic Box Model = padding + margin + border + width**


> width값이 전체 값을 정하는 거 아닌가?

> 여기서 중요한 점은 요소에 지정한 width와 height값은 단지 콘텐츠의 높이와 넓이를 말한다는 점이다. 실제 총 element의 크기를 구하려면 padding와 border 그리고 margin이 합해져야 한다.


```css
    div {
        width: 320px;
        padding: 10px;
        border: 5px solid gray;
        margin: 0; 
    }
```
따라서 div의 최종 width는 **width(320px) + padding(20px) + border(10px) + margin(0) = 350px** 이 된다. 이럴 경우에는 입력한 width의 값과 실제 총 element width의 값이 달라져 계산하기 어려워지고 복잡해질 수가 있다. 이런 문제점을 전체 스타일에 `border-box` 를 적용시킴으로써 문제를 해결할 수 있다.

```css
    *, *::before, *::after {
         box-sizing: border-box;
    }
```
이런 방식을 "universal box-sizing"이라고 부른다. 이렇게 하면 실제 입력한 width 값이 최종width가 된다. padding값과 border값을 width영역에 포함시켜 실제 최종 width는 **입력한 width(320px) + margin(0) = 320px** 값이 된다.
