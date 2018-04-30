### form

- js는 초기에는 form의 유효성 검사를 위해 주로 사용
- 'get' : url에 붙어서 날라감
- 'post' : body에 붙어서 날라감 key & value pair -> key는 form control요소의 name


### html FORM

```html
<form 
  method="post"
  action="serverURL">
  <input 
    type="password"
    id="password"
    name="password1"
    placeholder="Password"
    pattern="^[a-zA-Z0-9]{4,10}$"
    required>

```

---

### template-driven-form 

- NgForm, NgModel, NgModelGroup을 중심으로 동작.
- 단순한 폼에 적합. 길어지면 복잡해진다.


---

### reactive form

- FormGroup 인스턴스는 자식 FormControl, FormArray같은 인스턴스들을 그룹화하여 관리하는 최상위 컨테이너


1. 폼 그룹 객체를 생성한다 
```js
  const myFormGroup = new FormGroup({
    // 자식 폼 모델 인스턴스
  })
```