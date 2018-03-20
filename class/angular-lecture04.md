### Service
- 애플리케이션에서 단 하나만 존재. `singleton pattern`
- 컴포넌트의 관심사와 애플리케이션 전역 관심사를 분리하는데 사용
- Dependency Injection 을 사용 해 긴밀한 연결을 느슨하게?? (DI는 클래스기반 언어의 용어)


### 서비스 생성
- 특정 서비스의 생성을 사용자가 하는 것이 아닌 `injector`가 알아서 필요한 서비스인스턴스를 주입한다.
- app component는 greeting service에 의존한다. (app은 greeting에 의존성을 가짐)
- (npm install --dependencies 와 같은 개념)
- greeting service가 변경되면 app도 영향을 받음 - 긴밀한 결합 - 이 해결하기 위해 DI pettern을 사용


### 의존성 주입(Dependency Injection)
- 외부의 설정으로 뻬놓는다. 설정만 고치면 내용이 변해도 사용가능.

### service 사용하기
- service.ts는 자동으로 모듈에 등록되지 않는다 - 필요한 부분에 직접 등록해서 사용
- `module`혹은  `component` meta-data에 `providers`등록해서 사용.
- `component`에서 선언하면 해당 component와 그 자식만 사용가능
- `module`에서 선언하면 전역에 걸쳐서 사용가능 (단 한개의 service 인스턴스만 가능)


### how to use?
- 다양한 component가 자유롭게 service를 쓸 수 있으나 추적하기 어려울 수 있다.
- service안에 addTodo같은게 오는게 맞는지? 
- 혹은 component가 가지고 있는게 맞을지? (stateful - stateless component구조)
- service가 얼마만큼의 능력을 가질 것인지 정하는것이 중요!

---
## 용어 정리

### Dependency Injection
- one object supplies the dependencies of another object
- dependency injection is one form of `inversion of control`
- the client delegates the responsibility of providing its dependencies to external code(the injector) , the client is not allowed to call the injector code. It is the injecting code that constructs the services and calls the client to inject them.


### Inversion of Control (IoC)


---

## RxJS

### Reactive Programming
- 비동기 데이터 처리


---

**input의 종류들**
- 배열 : 동기
- Event : 언제 발생할지 모름 (비동기)
- ajax : 언제 response가 올지 모름 (비동기)
- ...
다양한 input에 따라 달라지는 로직이 아닌 통합된 로직을 갖게 하고 싶은 욕구 -> reactive programming

---
**observable**
- observables : 관측해야 하는 대상들
- observer가 변화를 감지한다.

---

**pull-scenario**
- 직접 요청하고 응답 받는다

**push-scenario**
- 외부환경에서 응답이 오면 반응
- reactive programming 방식

---

.sbscribe(
  // 여기에 observer를 정의 해준다.
  value => {

  },
  error => {},
  

)

---

- put : 레코드 전체 번경 payload 있음.
- patch : 일부변경 payload 있음
- delete: payload 없고 url에 아이디 줌.
---

**용어**
### Dataflow programming
