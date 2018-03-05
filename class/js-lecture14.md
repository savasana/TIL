## Server Side

- 상태변화를 감지하고 변도사항을 서버에 등록, 결과값을 전달
- 상태변화를 자동 감지해주는 툴을 사용해 프레임워크와 쉽게 관리가능(앵귤러,..)
- 서버사이드가 할일 (정적파일제공, REST API, Database)
- 주로 Java(spring) 사용 : 안정적이나 세팅이 어려움, 대규모 프로젝트
- 요즘은 Python, node : node는 빠르게 빌드가능, 간단하고 반복적인 일들에 적합(sns)복잡한 연산에 취약

## Node.js

- Non-blocking I/O : 거의 100% 비동기처리
- Single Thread Event Loop
- CPU연산이 많은 일들에는 취약
- 간단한 I/O를 다량으로 하는 일들 (sns, 메신저등)
- Socket.io와 함께하면 실시간 통신을 쉽게 구현할 수 있다.
- 서버가 클라이언트에게 메세지를 보내는것은 힘든 기술 (socketio,pwa로..사용?


## npm

```json
"dependencies": {
    "node-emoji": "^1.5.1" // ^없으면 특정버전 고정
  },
```

^(캐럿)은 이후 해당 패키지의 버전이 업데이트되었을 경우, 마이너 버전 범위 내에서 업데이트를 허용한다는 의미이다. ex) 1.8.4 -> 1.9.0 은 오케이 / 1.8.4 -> 2.0.0 은 허용안함

```js
$ npm install something --save-exact
```


### Node.js 모듈

- module.exports / exports 를 통해 정의하고 외부로 공개
- require 함수로 import


---

### exports

- 값을 할당할 수 없고 공개할 대상을 exports객체에 프로퍼티, 메소드로 추가

##3 module.exports 

 - 객체에 하나의 값을 할당
