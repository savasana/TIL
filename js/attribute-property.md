
## 'HTML attribute' and 'DOM property'

HTML을 작성할 때, attribute를 HTML요소에 직접 정의할 수 있다. 이렇게 작성한 코드를 브라우저는 파싱을 통해 그에 맞는 DOM노드를 만든다. 이렇게 만들어진 노드는 객체이고, 객체이기 때문에 property를 가진다. 

예를 들어, HTML요소 `<input type="text" value="name">` 는 type, value 2개의 attribute를 가지고 있다. 이 코드는 브라우저 파싱을 통해 HTMLInputElement 객체로 생성되고 다양한 property를 포함하게 된다.(attributes, autofocus, baseURI, checked, childElementCount, childNodes, children, classList, className,...) 
여기에서 이 DOM노드 객체가 가진 property는 객체의 property이고, attribute는 객체의 attribute라는 property에 속한 객체들이다. 

HTML요소가 DOM노드로 변환되어 생성될 때, DOM노드 객체의 property들은 이전 html요소의 attribute와 연관된 것들로 비슷하거나 같다. 하지만 모든 attribute가 property와 1대 1로 매칭 되지는 않는다.
---

`<input type="text" id="the-input" value="name">`로 형성된 DOM노드 객체는 `id`, `type`, `value`의 attribute와 연관된 property를 가진다. 

- `id` **property**는 attribute의 반영으로, 같은 값을 나타낸다. 
- `type` property는 `type` attribute의 반영이지만 알 수 있는 타입에 한해서만 작동한다. input type="foo" 일 때는 attribute는 foo를 나타내지만 property로 접근하면 text를 나타낸다. 
- `value` property는 `value` attribute의 반영이 아니다. property는 현재 input값을 나타낸다. 사용자에 의해 변화된 값을 반영한다. 따라서 property와 attribute값이 일치하지 않는다. value attribute는 초기 값을 나타낸다. 

이와 같이 DOM 노드 객체의 property와 HTML요소의 attribute는 요소에 따라 같을 수도 있고 다를 수도 있으므로 주의하자. 
기본적으로는 객체 property를 사용하도록 한다.

---

### attribute
- attribute는 HTML자체가 가진것.
- attribute의 값은 항상 **string(문자열)**이다.
- `<div id="test" class="button"></div>` HTML태그 안에 표현되는 것들을 attr라고 한다.
- `getAttribute('value')`, `setAttribute('class','header')`
---

### property
- 파싱을 통해 형성된 DOM노드 객체가 가진 것. (객체니까 property 있음) 
- property 중에 attributes라는 property가 있고, 이안에 attribute와 연관된 property들이 생긴다. 
- 이는 상황에 따라, 요소에 따라 같을 수도 있고, 다를 수도 있다.
- `element.id`, `element.className`, `element.value`


---

### type differences

- DOM property는 attribute와 달리 값이 항상 문자열이 아니다.


```html
<input id="input" type="checkbox" checked> 
```

```js
alert(input.getAttribute('checked')); // 값은 empty string
alert(input.checked); // the property 값은 true
```

위와 같이, `checked`의 attribute값은 빈문자열이고, `checked`라는 property의 값은 Boolean의 true이다.

---

```html
<div id="div" style="color:red;font-size:120%">Hello</div>
```

```js
// string
alert(div.getAttribute('style')); // color:red;font-size:120%

// object
alert(div.style); // [object CSSStyleDeclaration]
alert(div.style.color); // red
```

style attribute는 문자열인 반면 style property는 object를 나타낸다.

---

### summary
- attribute는 HTML에 쓰인 것! 
- property는 DOM객체에 들어있는 것! 

- DOM property를 사용하고, 필요한 경우에만 attribute를 사용 권장. 
- 스탠더드가 아닌 attribute가 필요한 경우 : dataset attr사용 
- href나 value처럼 html에 쓰인 값이 필요한 경우 attr사용.

---


**참고링크**
- [javascript info - dom attributes and properties](https://javascript.info/dom-attributes-and-properties)
- [attribute and property](https://stackoverflow.com/questions/6003819/what-is-the-difference-between-properties-and-attributes-in-html)
- [html attribute vs dom property](http://joji.me/en-us/blog/html-attribute-vs-dom-property)