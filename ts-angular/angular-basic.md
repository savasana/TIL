### Angular

- [angular doc](https://angular.io/guide/)
- HTML templates을 만든다.
- component class를 통해 템플릿을 관리한다.
- 컴포넌트와 서비스를 묶어 모듈화 한다.
- root module을 bootstrapping해서 앱을 실행한다.(root module을 실행하면 그 안에 있는 다른 것들도 실행된다는 의미) - root momule is a main module that starts a whole process

---

### modules
- 앵귤러 앱은 모듈러이고 자체 모듈시스템인 NgModules를 사용한다.
- 모든 앱은 최소한 한개의 root module인 NgModule 클래스를 가지고 있다.(AppModule)
- 작은 앱은 한개의 root module이 전부일 수 있고, 큰 앱은 더 많은 feature module을 가질 수 있다.
- NgModule은 `@NgModule` 데코레이터를 가진 클래스이다.

--
### decorator
- class decorator : `@Component`, `@NgModule`, ..
- property decorators inside classes : `@Input`, `@Output`
- method decorators inside classes : `@HostListener`
- parameter decorators inside clas constructors : `@Inject`

**class decorator**
- top-level decorators라고도 하며 클래스의 의도를 나타낼때 사용한다.
- `component`, `module`과 같은 특정 클래스를 나타낼때 사용. 
- 정의만으로도 어떤일을 하는 클래스인지 알 수 있다. (클래스안에 코드가 없어도)


**property decorator**
- 클래스 안에서 특정 property를 나타낼때 사용
- `@Input` : input바인딩을 원하는 프로퍼티에 사용

```js
import { Component, Input } from '@angular/core';

export class ExampleComponent {
@Input()
exampleProperty: string;
}
```

```html
// 템플릿
<example-component
  [exampleProperty]="exampleData">
</example-component>
```

---
### components
- 컴포넌트는 view의 부분을 컨트롤한다
- 클래스 안에 컴포넌트를 작성한다. 프로퍼티, 메서드 api를 통해 view와 interact한다.

---

### templates
- 컴포넌트의 view를 짝이 되는 template을 통해 정의한다.
- 템플릿은 html의 형태로 앵귤러에게 어떻게 렌더할지 알려주는 역할.

---

### metadata
- 메타데이터는 앵귤러에게 클래스를 어떻게 처리할지에 대한 정보 제공
- @Component 에 사용되는 metadata (selector, templateUrl, providers,...)

---

### data binding
- {{ data }} / [property]="data"
- (event) = "expression"
- [(ngModel)]="property" (주의)

two way data binding은 상태가 마법과도 같이 바뀐다.속도가 느리다. implicit. 
one way data binding은 빠르다. explicit. 데이터가 한방향으로 흐른다. 컨트롤할 수 있다.

---

### directives
- 앵귤러의 템플릿은 directives의 지시에 의해 DOM을 변화시킨다.(다이나믹하다)
- structural directives : DOM에 element를 더하고,지우고,교체하면서 레이아웃을 바꾼다.
- attribute directives : 존재하는 element의 동작이나 모습을 바꾼다.

```html
// structural directives
<li *ngFor="let item of items"></li>
<app-item-detail *ngIf="selectedItem"></app-item-detail>
```

```html
// attribute directives
<div [ngStyle]="currentSyltes"></div>
```


| While a component is technically a directive, components are so distinctive and central to Angular applications that this architectural overview separates components from directives.

---
