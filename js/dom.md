## What is DOM?

### Brief history of DOM

오늘은 그동안 배운 자바스크립트에서 한단계 더 나아가는, 기다리고 기다리던 DOM을 배웠다. DOM의 역사는 90대말 일어난 '브라우저 전쟁'과 밀접하과 연결되어 있다. 자바스크립트와 마이크로소프트의 JScript는 웹개발자들이 클라이언트사이드와 상호작용할 수 있는 웹페이지를 만들도록 하였고 사용자 이벤트를 감지하고 HTML 도큐먼트를 수정하는 제한적인 기능들이 DOM의 시작이었다. 후에 ECMAScript가 표준화가 되고 나서 W3C DOM Working Group은 DOM의 표준을 작성하기 시작했고 그렇게 DOM Level 1이 탄생했다.

DOM의 주요 표준화는 2004년까지 W3C에서 이루어 지다가 WHATWG(Web Hypertext Application Technology Working Group)가 작업을 이어받아 living document라는 명칭으로 공개하고 있으며 W3C는 WHATWG 표준의 안정화된 스냅샷(단편)을 발행하고 있다. WHATWG의 스냅샷인 DOM Level 4가 2015년 발행되었다.

---

### DOM

HTML 페이지와 같은 도큐먼트를 렌더링하기 위해서는 대부분의 브라우저는 내부적으로 DOM이라는 모델을 사용한다. 도큐먼트의 노드들은 트리 구조로 이루어져 있고 이는 DOM tree라고 하고 최상위 노드를 'Document object'라고 한다. 

웹페이지가 로드(load)되면, 브라우저는 HTML 도큐먼트를 바탕으로 DOM을 형성하고 이는 자바스트립트과 도큐먼트 사이를 이어주며 자바스트립트가 HTML요소나 속성을 조작할 수 있게 만들어 주는 인터페이스 역할을 한다.


The Document Object Model is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

A Web page is a document. Th DOM represents that same document so it can be **manipulated**. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as javaScript.


---

### DOM and JavaScript

자바스크립트는 DOM을 통해 도큐먼트와 그의 객체에 접근할 수 있다. DOM은 프로그래밍 언어가 아니지만 자바스크립트는 DOM없이는 웹페이지나 HTML 도큐먼트, 혹은 다른 요소에 대한 그 어떤 모델이나 정보를 갖지 못한다. (그만큼 중요한 역할)
도큐먼트내에 모든 element는 DOM의 부분이고 따라서 자바스크립트에 의해 접근이 가능하고 조작가능하다.


JavaScript uses the DOM to access the document and its elements. The DOM is not a programming language, but without it, the JavaScript language wouldn’t have any model or notion of web pages, HTML documents, XML documents, and their component parts(elements). 

Every element in a document is a part of the document object model for that document, so they can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

---

### Document

A document node represents every document as the root. The document element is the outermost element in the document within which all other elements exist. There can be only one document element per document. In HTML pages, the document element is always the `<html>` element.

---

### NODES

`Node`는 DOM API 객체 타입들이 상속을 받는 인터페이스 이고 여러개의 타입들을 비슷하게 묶어준다.(같은 메서드를 상속받거나..)
Node의 메서드나 프로퍼티를 상속?받는 인터페이스에는 `Document`, `Element`, `CharacterData` - `Text`,`Comment`, `DocumentFragment`, `DocumentType`등이 있다.

**주요 노드들**

- `Document` : entry point into the web page's content.
- `Element` : HTML요소로 부모자식관계를 형성. (도큐먼트 내의 모든 객체가 상속받는 가장 기본 클래스?)
- `Attr` : element의 일부
- `Text` : element의 자식. DOM tree의 가장 끝(밑)


Node is an interface from which a number of DOM API object types inherit; it allows these various types to be treated similarly, for example inheriting the same set of methods, or being tested in the same way.

The following interfaces all inherit from Node its methods and properties: Document, Element, CharacterData (which Text, Comment, and CDATASection inherit), ProcessingInstruction, DocumentFragment, DocumentType, Notation, Entity, EntityReference.

---

### Selectors API

- `title.textContent` : 텍스트로 인식 (마크업도 문자열로 인식)
- `title.innerText` : CSS 영향 받는다 (display, visibility로 숨기면 조작할 수 없음)
- `title.innerHTML` : html직접 입력 가능

---

- `document.getElementById('header')` 
- `document.getElementsByClassName('items red')` : 유사배열 live `HTMLCollection`
- `document.getElementsByTagName('p')` : 유사배열 live `HTMLCollection`


---
**query Selector** : CSS 선택자를 바로 쓸 수 있다. 굉장히 유용

- `document.querySelector('.main-header')`
- `document.querySelector('input[type ="submit"]')`
- `document.querySelector('.list-group-item:last-child')`
- `document.querySelector('.list-group-item:nth-child(2)')`

**querySelectorAll** : 여러개 선택, non-live `nodeList` 반환

- `document.querySelectorAll('li:nth-child(odd)')`
- `document.querySelectorAll('li:nth-child(even)')`

---

### Traversing the DOM

**Find Parent**

- `itemList.parentNode.parentNode`
- `itemList.parentElement`

**Find Children**

- `itemList.childNodes` : white-space 텍스트까지 인식하므로 주의! `nodeList`
- `itemList.children` : white-space 무시! `HTMLCOllection`

**Find first,last child**

- `itemList.firstChild` : white-space 인식
- `itemList.lastChild` : white-space 인식
- `itemList.firstElementChild` :  on element
- `itemList.lastElementChild`: on element



---

### Links

- [WHATWG DOM Living Standard](https://dom.spec.whatwg.org/)
- [W3C Selectors lv2](https://www.w3.org/TR/selectors-api2/)
- [W3C DOM](https://www.w3.org/TR/dom/)
- [MDN : Introduction DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [how browsers work](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)

