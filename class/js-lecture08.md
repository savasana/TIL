# js lecture 08

## DOM and Event
---

- EventHandler 중요
- 왜 jquery를 점점 안쓰는가? - JS가 DOM에 종속된다 - html이 변하면 JS도 변해야 한다. html은 수시로 변한다. 비효율 
- html이 바뀌어도 js가 바뀌지 않게 하는 구조가 중요. (angular, react)
- DOM은 불편한 설계 - 실무에서는 DOM API를 실제로 쓸일이 거의 없다.
- DOM은 cross browsing이 중요
- browser support는 끝이 없어 - polyfill사용

---

### DOM ( Document Object Model )

- Document : html, css, javascript 
- Object : key, value pair ( properties and method )
- Model :  

html css js가 하나의 객체화가 되어서 어쩌구 저쩌구 하는 것.

---

imagine we have a to do app
DB  / Json / object
db에서는 파일, 전달할때는 json 포맷 (문자열) , 클라이언트에서는 객체화

---

주소창에 주소를 치고 페이지가 나타날때,
html을 load한다 그리고 한줄 한줄 읽어나간다 (parsing) 그러다가  link ref / style을 만나면 파싱을 멈추고 CSS 를 load하고 파싱한다.
각각 tree 구조를 만들고 두개 css html이 합쳐져서 렌더트리를 형성하고 렌더링을 통해 디스플레이를 한다.
js는 css html과 다른 엔진사용. js는 css html을 조작.


---

객체는 무엇인가?
객체를 왜 만드나?
다양한 데이터를 하나로 묶기 위해서

---

js는 DOM을 control 할 수 있는 능력 ( API를 통해서 ) 

---
DOM이 하는 일
- 모델 구성 (로드와 파싱을 통해서)
- 각 요소에 접근 과 수정
---

- document 가 최상위 진입점 (document의 부모는 Window)
- document안에 요소들을 node라고 한다
- document 노드  이렇게 부른다
- 요소는 tag명 <div> , <ul> , <li>
- 어트리뷰트는 요소 뒤에 붙는 것들 class = “name ” ...
- 요소와 어트리뷰트는 항상 링크가 되어있어서 찾아갈 수 있어야 한다. (형제관계이다)
- 모든 요소노드는 텍스트 노드를 **자식**으로 가지고 있다. <div>here</div>
- 여러개 요소를 선택하면 - 유사배열객체로 리턴한다

---

DOM을 통해 조작하기 위해서는
- 요소를 선택 (query) - 단서를 주고 그에 해당하는 결과를 달라 
- 선택 후 탐색 traverse

---
node는 총 4가지가 있다.
- document, text, element, attr
- htmlelement - 요소마다 특징이 달라서 태그마다 다 다르고 전체의 공통된 특징은 부모 자식 상속을 통해서...

#### document.getElementById(id)
- id에 맞는 HTMLParagraphElement …등..를 반환한다.
- HTMLElement를 상속받은 객체를 반환한다.

#### document.querySelector(cssSelector)
- .one, CSS문법 그대로 써준다
- 여러개일 경우 첫번째만 반환한다

#### document.querySelectorAll(cssSelector)
- 유사배열인 nodeList로 반환 (non-live)

#### document.getElementsByClassName(class)
- 요소노드를 모두 선택해 유사배열을 반환
- 유사배열인 HTMLCollection반환 - live
- live :  결과를 실시간 반영 - 조작하기 어려움

#### document.getElementsByTagName(tagName)
- 태그명은 바뀌지 않는다. (지우고 다른거 줄 수는 있지만...)

---

### Traversing


#### parentNode
- 메서드가 아닌 프로퍼티로 찾아간다.
- something.parentNode;
- 자식까지 다 가져옴으로, 메모리 많이 먹을 수 있어 .

#### firstChild, lastChild
- property로 찾아간다
- 텍스트영역도 자식으로 인식해서 제대로 찾기 어려움

#### hasChildNodes()
- boolean으로 반환

#### childNodes
- 자식노드 컬렉션을 반환
- nodeList

#### previousSibling, nextSibling
- elem.nextSibling;

---

요소와 속성은 형제 
요소와 텍스트는 부모 자식 관계

---
### Manipulation 조작

- `.nodeName`  : 노드 이름 LI, DIV, ..
- `.nodeType` : 4가지 중 하나
- `.nodeValue`

---
- `.hasAttribute`
- `.setAttribute`
- `.getAttribute`
- `.removeAttribute`

---
- `.innerText` : 비표준, 사용하지 말것
- `.innerHTML` : 스크립트를 넣으면 브라우저에 따라서는 실행됨.  해킹에 위험이 있음으로 내부적으로 script를 걸러야된다. (untrusted data처리)

---
#### insertAdjacentHTML(position,string)
- position: before begin, after begin, befriend, afterend


---
### Event
- html요소에서 이벤트가 발생.




---
# DOM


The Document Object Model is a programming interface for HTML and XML documents. It represents the page so that programs can change the condiment structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

A Web page is a document. Th DOM represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as javaScript.

---

### DOM and JavaScript

JavaScript uses the DOM to access the document and its elements. The DOM is not a programming language, but without it, the JavaScript language wouldn’t have any model or notion of web pages, HTML documents, XML documents, and their component parts(elements). 

Every element in a document is a part of the document object model for that document, so they can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

---

### Document

A document node represents every document as the root. The document element is the outermost element in the document within which all other elements exist. There can be only one document element per document. In HTML pages, the document element is always the <html> element.

---

### The Node Type
Every node has a nodeType property that indicates the type of node that it is.

- ELEMENT_NODE
- ATTRIBUTE_NODE
- TEXT_NODE
- DOCUMENT_NODE
- …(앞에 Node.생략했음)


---

### The Document Type

In browser the document object is an instance of HTMLDocument.
The document object is a property of window and so is accessible globally.


---





