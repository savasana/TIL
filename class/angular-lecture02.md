### template

- template & component : 관심사가 다른것은 분리하여 관리 -> 유지보수
- template은 view를 형성하고 component는 model.(view를 컨트롤)


### Data binding

- 구조화된 웹앱을 구축하기 위해서는 뷰와 모델의 분리가 필수적
- view & model은 협력해서 html을 만들어 내는것 - interact 필요
- 기존 js는 직접 DOM에 접근해서 조작가능 - DOM이 바뀌면 연결도 끊기는 단점
- 로직이 DOM을 조작한다 - DOM이 변경되면 로직도 바뀌어야한다. 디자인이 바뀌면 큰문제.
- 앵귤러는 DOM에 직접 접근하지 않고 template과 component클래스의 상호 관계를 선언
- html은 선언형 방식 (배열처럼 필요한 요소들을 가져다가 쌓는다) - template도 선언형으로 작성

```html
<h1>
  {{title}}
</h1>
```

---

### Change detection

- Two-way binding 내부적으로 루프가 계속 돌아서 체크 (이전의 angular.js 방식)
- 현재 angular2는 One-way binding 을 지원한다
- [(ngModel)]도 사실상 이벤트바인딩 + 프로퍼티 바인딩을 shorthand 한것.


- 어떻게 마법과 같이 template이 업데이트 되는가? - zone.js에 의해!
- DOM 이벤트 발생시 / Timer 이벤트 발생시 / Ajax , Promise
- 3가지를 Zone.js가 항상 감시하고 변화되면 DOM에 알려줌.

---

### Data binding 종류

**component -> template**
- interpolation binding
- property binding
- attribute binding
- class binding
- style binding

**template -> component**
- event binding

**template <-> component**
- two way data binding

---

### Interpolation binding
- {{ expression }}
- **expression is any valid unit of code that resolves to a value**

```ts
export class AppComponent {
  // 왜  var없나 - ts 클래스 문법에서는 var생략
  name = 'Angular';
  age = 20;
  admin = true;
  address = {
    city: 'Seoul',
    country: 'Korea'
  };

  sayHi() {
    return `Hi! my name is ${ this.name }.`;
  }
}
```

---

### Property bindidng

- property는 객체내부에 있는 애들..
- html을 로딩하고 파싱을 통해 DOM트리로 변환(객체화한다) - DOM은 객체의 덩어리
- DOM에서 property는 html의 어트리뷰트들 (value, innerHTML, src, ... - DOM API에서 사용했던 것들?)

- 프로퍼티 바인딩은 컴포넌트 클래스의 프로퍼티(멤버변수)와 템플릿 간의 단방향 바인딩(One-way binding)
- [propertyName]="expression"
- <input type="text"> // type은 html어트리뷰트 , text는 문자열의 값
- <input [value]="name"> // [value]는 dom객체의 프로퍼티(=html의 어트리뷰트)에 name을 **할당**

- <p [innerHTML]="contents"></p> innerHTML은 p라는 DOM객체가 가진 프로퍼티

**HTML attribute와 DOM property를 구분할것**
[attribute and property](https://stackoverflow.com/questions/6003819/what-is-the-difference-between-properties-and-attributes-in-html)
- input.value  // value property
- input.getAttribute('value') // value attribute


### attribute binding


### class binding
- `[class.text-large]="isLarge"` //isLarge 는 Boolean으로 나올 수 있는 값
- `[class]="class-name-list"`
- 주로 하나의 클래스를 추가,삭제할때 사용. 여러개를 한꺼번에 지정할 때는 `ngClass`라는 directive사용 편리.

### style binding
- `[style.background-color]="값을 줄 수 있는 expression"`
- `[style.background-color]="isActive ? 'red' : 'blue'"`
- `ngStyle` directive있음

### event binding
- `(event)="statement"`
- statement: 이벤트핸들러를 호출하는 함수 혹은 직접구문입력
- expression 또한 expression statement이다.
- statement를 써야하는 곳에는 expression 도 쓸 수 있다. / 단, expression을 써야하는 곳에는 statement 쓸 수 없다.

### two-way binding
- `[(ngModel)]="property"` 
- ngModel은 상태가 변화하는 요소들에만 쓸 수 있다. input같은 애들..

 
 ---

 ### Built-in directive
 - component directives : @Component
 - attribute directives : ngClass, ngStyle, 모양이나 동작을 제어
 - structural directives : ngFor, ngIf, ngSwitch , DOM레이아웃을 변경


---

- component에서 template가서 선택하는건 no!! [(ngModel)]등을 활용해 접근할것.

