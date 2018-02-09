# Software Engineering 01
#lecture

teacher is an solution architect, team builder?


### Software Engineering
- 사람이 일할 수 있는 양을 수치화 하는것?
- [Man-hour - Wikipedia](https://en.wikipedia.org/wiki/Man-hour) amount of work performed by the average worker in one hour.

- - - -

### 개발 과 구현

### Development
- 분석, 디자인, 구현
- 시스템을 설계하고 분석해서 구현하는 모든 과정 ( 개발자 )

### Implementation
- installation of a computer system or an information system
- 도구를 사용해서 작성하면 구현이라고 한다 ( 코딩만 하는 사람 )

- - - -
### 소프트웨어 공학의 트랜드
- DevOps
- mobile first aproach
- security
- cloud computing 
- web + mobile app integration : progressive web app(web을 native app처럼 보이게), instant app(앱 안깔고도 앱처럼 효과는 내는 것)

- - - -

### DevOps
- Development + Operation 
- rapid , frequently, reliability
- 예전에는 개발과 운영이 분리되어 존재. 운영팀은 사용자와 개발자 간의 중간자 역할. 중간 절차가 너무 길어 문제점이 많았음.  cloud computing이 활성화 되면서 operation의 일이 많이 줄었다.
- 운영과 개발을 합해 커뮤니케이션 리소스를 줄이고, 안정적인 서비스를 운영할 수 있음.
- 인건비를 감축하기 위한 목적도 있음
- google cloud , amazon web service 에 관리를 맡기는것은 noOps라고함 ( 보통 웹서비스, 추천시스템, 소비자의 피드백이 덜 중요한 상품은 가능)

- - - -

### Software Development Life Cycle
- 개발보다 요구사항 분석이 가장 중요하다.
- 요구사항이란 (requirement) : 무엇이 구현되어야 하는가에 대한 명세
- 요구사항을 구현할 수 있을 만큼의 정보를 얻는게 중요. ( 결제서비스 만들어주세요, 왜 하려고 하죠? 의도파악, 어떻게 결제하실거죠, 어떤 카드를 쓰실거죠, 상품은 어떤종류가 있고, 등등 사전정보를 제대로 얻는것도 중요)

- - - -

### Requirements Analysis
- 요구사항 유도 와 수집 : 클라이언트와 미팅을 통해 요구사항을 결정하는 작업

- - - -
### Requirements Layer
1. business requirements : vision, scope 문서
2. user requirements : use case documents
3. system 및 기능 요구사항 : 요구사항 명세 ( 구체화 시키는 작업 )

- - - -

#### Business Requirements
- why? 왜 프로젝트를 수행하는지
- 고객 ( 사장님 + 실제 사용자 ) 이 얻을 수 있는 이득

#### User Requirements
- 실제 유저(사용자)가 무엇을 할 수 있는지, 무엇을 얻을 수 있는지 
- use case diagram : (ex 사용자, 웨이터, 쉐프, 직원 의 행동 관계도 - 주문하다, 먹다, 조리하다, 서빙하다, 등등 객체지향 관계도  )
- user scenario : persona, …
- user stories : user story map  -  단계별로 구현하고 싶은 핵심기능으로 나누고 
- - - -
#### Functional Requirements
- 개발자가 이 제품의 “무엇”을 개발할 것인지
- ‘~해야한다’ ( 회원가입 아이디는 이메일로 해야 한다. /  페이스북, 인스타그램, 이메일을 사용할 수 있어야 한다. ) 강력하게  나타내야 한다.
- - - -
#### system requirements
- - - -
#### Business Rules
- structure 요구사항, 제약사항 명세
- “유저 로그인을 위해서는 페북아이디가 있어야 한다.”
- 가장 중요 
- - - -
#### quality Attribute
- 품질에 대한,
- 소프트웨어 커버리지 ( 리스트는 몇개, 동시 접속자 등등)

- - - -
#### Constraint
- 법, 기술, 표준, 업무 제약조건 명세

- - - -

### Software Development Lifecycle Process Model

1. Build and Fix Model
	- 설계없이 일단 개발, 만족할 때까지 수정 / 남는게 없다
2. Waterfall Model
	- 각 단계가 끝나기전에 넘어가지 않는다 / 순차적인 개발 모델 / 정확도, 완벽도, 안정성 추구
3. Prototype Model
	- 개인 작업
4. Spiral Model
	- 단계를 계속 반복 / 대규모 고비용 프로젝트 / 느리지만 버그가 적다. 
- - - -
#### Agile 방법론 : eXtrem Process (XP)
- scrum  
- daily scrum :  master가 할일을 붙여놓고 - 전체 회의 및 일의 분배 - 
- TDD (test driven development) 테스트 코드를 먼저 쓰고 본코드 작성 
	- 생길 수 있는 오류 에러 가능성을 다 작성하고 코드를 작성
	- 객체지향적 : 기능 단위로 개발 

- - - -
### Data & Database

- DB (database) : 체계화된 데이터의 모임
- DBMS (DataBase Management System) 관리해주는 툴
- Oracle ( 안정적, 비싸다 ), Mysql, MariaDB, 

- - - -

#### 데이터의 성격
- 데이터의 무결성 ( 결함이 없음 )
- 데이터의 중복방지
- 보안
- 성능향상

#### file system 과 database의 차이점


- - - -
### RDBMS vs NoSQL
- PostgreSQL, MySQL, …
- RDB : 엑셀파일과 비슷해 
	- sheet는 db에서 테이블 
	- 가로: 데이터쌓이고 세로는 인덱스
- 조작언어, 제어언어, 
- 관계형 database, 정형 database : row, column으로 이루어져 있음 (테이블 구조를 바꿀 수 없음)
- 스키마가 고정(schema?)
- - - -
### NoSQL
- scheme-less
- like 파일철 같아. ( 그 안에 한장 한장 정보를 담는다 )
- 형태 : key & value(벨류 안에 또 키&벨류 들어갈 수 있다), document, column
- MongoDB, CouchDB, Cassandra(데이터분석할때 많이 써), Redis
- 잦은 수정시 저하 - raw데이터 쌓을 때나, 자주 들여다 보지 않을 때 사용

- - - -
User DB는 RDBMS
로그 데이터, 결제 데이터, 1년뒤에 지워도 되는 것들은 NoSQL
- - - -
#### document vs key-value
- - - -
#### 외부스키마, 개념스키마, 내부스키마

- 외부스키마 : 내가 뭘 했을때 보이는것 / 사용자와 만나는 부분 / 조회했을때 얻게되는 결과들
- 개념스키마 :  테이블간에 데이터가 어떻게 연결되고 왔다갔다 하는지 **가장중요**
- 내부스키마  :  실제 데이터를 어떻게 저장하는지 DBMS가 알아서 하는 부분.

- - - -

#### SQLite3

![](se-lecture01/Screen%20Shot%202018-02-09%20at%2016.20.11.png)
- - - -
 `select name from user where math>90;` -> 수학점수 90점 이상인 사람 찾아줘
`drop table user;`  -> user 삭제

- - - -
