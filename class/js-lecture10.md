### Ajax

- 서버에 원하는 것(html-파일)을 요청한다(request)
- 요청한 것들 받는다
- 결과를 html로 만는다(로드 - 파싱 - 렌더트리생성 -렌더)
- AJAX를 써서 서버와 통신 한다

- Ajax는 URL을 바꾸지 않고 (화면을 깜빡이지 않고) 갱신가능하게 해줌
- SEO 이슈가 발생 (검색이 안되므로)
- 그래서, 어떻게 해결했을까?


---

- request, response 단방향 통신 (무전기처럼 동시에 통신할 수 없다)
- 단 방향이어서 페이지를 받을 때마다 기존 이력은 사라짐 ?
- 서버와 통신한 이력이 어딘가 저장되어야 함.다양한 해결책이 생겨남(쿠키 -> 세션 -> 토큰) 

- 이전에는 `<html>~</html>`로 끝나는 완전한 html을 주고 받았다.
- 따라서 일부가 바뀌어도 전체를 다시 요청해서 그려야 했다.
- ajax는 필요한부분(바뀌는 부분만)을 부분(REST API의 형태로)으로 받아서 갈아 끼는것


---

- server가 json의 형태로(html로 만들지 않고) 보내서 client에게 넘기는것(클라이언트쪽에서 만들어야함)
- server쪽에서 html로 만들어 보내는것 - 서버렌더 / 반대 - 클라이언트 렌더
- 서버렌더는 seo도 좋고 깔끔하지만, 서버쪽 일이 많아지고 돈이 많이 드는 단점
- 주고 받는 데이터는 어디에 담아야 하는가? -> JSON

---

### JSON

- JavaScript Object Notation 자바스크립트 표현기법을 활용한 포맷
- 클라이언트와 서버 간 데이터 교환을 위한 포맷
- 텍스트 : 문자열이다. 왜? 
  인터넷 통신 규약(http)은 데이터를 문자열로 주고 받는 것이다.
  문자열 - ASCII CODE를 사용한 문자열이겠지!
- JSON은 반드시 큰 따옴표로 둘러싸야 한다.
- 타입에 따라서 문자열에 ""사용, 프로퍼티명에도 ""사용

---

### `JSON.stringify`

```js
var o = {
  name: 'Yohan',
  gender: 'male',
  age: 20
}
JSON.stringify(o)
```

- 객체를 JSON으로 변환 , type은 string
- 인자로 array배열을 받을 수도 있다.

---

### `JSON.stringify(o, null, 2)`

- JSON을 보기 편하게 만들어준다.
- 확인할떄 용으로 사용

---

### `JSON.parse(strObj)`

- 서버로 부터 받은 JSON 문자열을 객체로 변환한다.
- 인자로 배열을 사용할 수 있다.

---

### XMLHttpRequest 

- 생성자 함수네!
- 브라우저는 XMLHttpRequest 객체를 이용하여 Ajax 요청을 **생성하고 전송**한다.
- 기본은 비동기 방식

**방법은 정해져 있음**

```js
//  1. 객체를 생성한다
var xhr = new XMLHttpRequest();
// 2. 준비 : request를 오픈한다 - GET방식으로 /users로 통신할거다
xhr.open('GET', '/users');
//  3. request를 전송한다
xhr.send();
```

---

### `XHMLHttpRequest.open(method, url[, async])`

- method : GET, POST, PUT, DELETE, ...
- url : 서버의 url
- 통신을 준비하는 단계 (실제 통신은 send를 호출했을 때 이루어짐)

---

### `XHMLHttpRequest.send()`

- 요청을 보낸다, 어떻게? 문자로, 어떤 문자로? 
- header: 바디를 위한 메타 데이터 (html head와 유사하다)
- host : 서버를 확정할 수 있는 ?? 정보??
- 동일 출처 원칙에 의해 한번 통신한 호스트와 계속 통신해야함
- 실제 데이터는 body 에 있음 이를 페이로드 라고 한다.
- GET은 주소창에 붙어서 날라가고 (페이로드없음), POST는 안보이는 차이(보이지 않을뿐 없는것은 아님)
(헤더는 바디를 불러싼 짐차이고 짐은 실제 데이터)

ex) suhjohn.gitbooks.io/nunum-api

---
### `XMLHttpRequest.setRequestHeader`


---
### Ajax responce

---


---
- html에서 head : 웹 문서에 대한 메타 데이터 (title제외하고 표시 안됨)
- 웹서버 , 데이터베이스서버, ...
- MVC : Model View Controler 전통적인 architecture
- CBD : Component Based Development (angular, react..)
