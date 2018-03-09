## Type Script

# typescript
- type을 지원한다. (js는 loosely typed language)
- 파일 당  class 하나.
- oop language


### web pack
- 모듈 로더의 기능 (export, import가 일반 js안되므로)
- task manager - 컴파일러 기능 (sass, babel, ts..) - gulp grunt같은애들
- 여러개의 파일들을 합쳐준다

---


### class definition

**자바스크립트에서 클래스**
```js
class Person {
	//js는 class 안에 메서드만 올 수 있다.
	//변수(멤버변수)는 반드시 생성자메서드 안에서 지정
	constructor(name) {
		this.name = name;
	}
	walk() { console.log(`${this.name} is walking`)};
}
```

**타입스크립트에서 클래스**
```js
class Person {
	//ts는 멤버변수를 미리 선언.
	name: string;
	constructor(name) {
		this.name = name;
	}
	walk() { console.log(`${this.name} is walking`)};
}
```

- public, protected, private - 접근제한자
- private : 외부노출 X, 멤버도 볼 수 없음.
- protected : 외부노출 X , 상속받은 멤버끼리만 볼 수 있다.
- typescript는 멤버변수를 미리 선언하여야 한다.
- 기본 타입이 public (private, protected 꼭 지정 해줘야 함)

---

### public, protected, private

- public
	- 외부에서 참조해야 하는 것들
	- 공개되는 것들은 사용자들이 알아야한다
	- (사용할것을 공개해라.)
	
- protected
	- 


---

### Abstract class

abstract class는 클래스의 뼈대를 만들고 extend class에서 완성할 수 있도록 해준다.
abstract method()는 extend클래스에서 반드시 만들어야 한다.(안만들면 에러 발생)


---

### Interface

```js
interface Todo {
	id: number;
	content: string;
	completed: boolean;
}

let todos: Todo[];
```

---

### Angular

app.component.ts
- decorator
- new 로 클래스를 만들 필요가 없다.
- angular가 알아서 만들어주고 관리함
- 화면을 만드는 하나의 뷰 -> app.component.css + app.component.html + app.component.ts가 합쳐서 하나의 뷰
