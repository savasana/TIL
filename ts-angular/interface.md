### Interfaces

- interfaces only describe structure, **they have no implementation**
- they don't compile to any JavaScript code.
- DRY type definition allows for easy refactoring later
- interfaces are **open** and can be extended later on!

- 인터페이스는 커스텀 타입을 만들 수 있게 해준다.
- 자바스크립트 코드로 컴파일 되지 않는다. 구조를 설명하기 위한 용도.
- 인터페이스는 open되어있다. 객체를 지정할때 인터페이스 외의 프로퍼티를 추가해도 상관없음

```js
interface ICar {
  name: string;
  year: number;
  model: string;
}

let myCar: ICar = { name: 'Tesla', year: 2018, model: 'model S'};
```

---

### Extend Interfaces

- 클래스처럼 extends 해서 사용할 수 있다.

```js
interface User {
  email: string;
  password: string;
}

interface ConfirmedUser extends User {
  // User의 인터페이스도 포함
  isActive: true
}

interface Admin extends ConfirmedUser {
  adminSince: Date;
  // ConfirmedUser 포함(+User)
}
```