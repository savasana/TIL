## Javascript Lecture 01


### Language
- 자연어 ( 한국어, 영어, 일본어, ..) & 인공어 (programming language)
- 말 이나 문서로 표현할 수 있는 것
- 의사 전달의 목적
- 정확히 이해하기 위해서는 COMMON SENSE필요

### What is Programming?
- 컴퓨터에게 명령을 **효율적**으로 전하려는 기술
- 효율 = 우리가 전달하고자 하는 명령이 정확히 수행되는 것

---

### Syntax & Semantic

#### Syntax
- legal expressions
- grammer structure
`cat dog boy`

#### Semantic
- meaningful

`I are cool`  - syntax is correct but semantically wrong


---

### Computational thinking
- understanding
- decomposing
- modeling
- 문제 해결 능력 = 최종 결과 이행

**프로그래밍은 요구사항의 집합을 분석하여 적절한 자료구조와 함수의 집합으로 변환한 후 그 흐름을 제어하는 것이다.**


---

### Request & Response

- 브라우저의 주요 기능은 사용자가 참조하고자 하는 웹페이지를 서버에 요청( request)하고 응답(response)을 받아 브라우저에 표현하는 것
- 브라우저는 서버로부터 html, css, js파일을 응답받고, html,css는 렌더링 엔진의 HTML parser,CSS parser에 의해 parsing되어 DOM, CSSOM트리로 변환되고 렌더 트리로 결합된다.
- HTML 파서는 script 태그를 만나면 DOM 생성 프로세스를 중지하고 자바스크립트 엔진에 제어 권한을 넘긴다. 
- 자바스크립트 엔진의 실행이 완료된 후 브라우저가 중지했던 시점부터 DOM 생성을 재개한다. (script 태그의 위치에 의해 DOM의 생성이 지연될 수 있음)


---

### Expression

`5 * 10` - expression
`var x = 2;` - statement

Expression can be a statement but statement can not be an expression.

---

### Variable

- 유지할 핊요가 있는 값 -managing program state’

---

