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

---
### component
- each component 

---

### data binding
- {{ data }} / [property]="data"
- (event) = "expression"
- 

---

### property binding
- `[disabled]="isActive"` : with boolean expression 
- dynamic binding

### 