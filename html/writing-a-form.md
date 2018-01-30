## writing a form



### form이란 무엇인가?

form은 사용자가 웹서버로 정보를 제출(submit)할 수 있는 **인터렉티브 컨트롤**이 담긴 도큐먼트 섹션을 나타낸다.

> controls : text fields, buttons, checkboxes, range controls, color picker

### Writing a Form

- form은 `<form>` 태그로 시작하며 이안에 컨트롤이 위치하게 된다.
- 대부분의 컨트롤은 `<input>`요소로 나타낼 수 있고 기본값은 한줄의 텍스트 필드이다.
- `<label>`요소를 사용해 컨트롤에 이름을 붙일 수 있다. 
  `<label>`을 부모 요소로 사용해 `<input>`을 감싸서 연결하거나, `for`속성을 사용해 `input`과 연결해 줄 수 있다. 
- form안의 영역은 보통 `<div>` 혹은 `<p>`요소를 사용해 나타낸다.
- radio button은 `input type=radio`로 나타낸다. 
  이때 버튼들을 그룹핑 하려면 `fieldset`을 사용하고 `legend`로 타이틀을 줄 수 있다.
- 여러가지 중 하나만 선택할 경우 (피자 사이즈 처럼) input을 같은 `name="size"`로 묶어준다.
- `type=time`을 사용해 시간을 선택하게 할 수도 있다. min, max, step 속성을 입력 할 수 있다.step은 선택 시간의 간격을 나타낸다.(초단위로 계산)
- `<textarea></textarea>`를 사용해 "남기고싶은 메시지" 영역을 만들 수 있다.
-  `input`에 `minlength`, `maxlength` 속성으로 입력 글자 수 제한
- `input`에 `required`속성을 주면 필수 입력 영역으로 설정 할 수 있다


<br>

```html
<form>
  <div><label>Customer name: <input></label></div>
  <div><label>Email address: <input type="email"></label></div>
  <!-- 사이즈선택 라디오 버튼 그룹 -->
  <fieldset>
  <legend>Pizza Size</legend>
  <div><label> <input type="radio" name= "size"> Small </label></div>
  <div><label> <input type="radio" name= "size"> Medium </label></div>
  <div><label> <input type="radio" name= "size"> Large </label></div>
  </fieldset>
  <!-- 토핑 선택 체크 박스 그룹 -->
  <fieldset>
  <legend>Pizza Toppings</legend>
  <div><label> <input type="checkbox"> Bacon </label></div>
  <div><label> <input type="checkbox"> Extra Cheese </label></div>
  <div><label> <input type="checkbox"> Onion </label></div>
  </fieldset>
  <!-- type=time 원하는 시작시간, 끝나는 시간을 기본값으로 설정할 수 있다. -->
  <div><label>Preferred delivery time: <input type="time" min="11:00" ma="21:00" step="900"></label></div>
  <!-- 흔히 온라인 주문시 볼 수 있는 "배송시 요청사항" 같은 영역 -->
  <div><label>Delivery instructions: <textarea></textarea></label></div>
  <div><button>Submit order</button></div>
 </form>
```

<br>

<script async src="//jsfiddle.net/daheoh/b3v74fz2/1/embed/result/"></script>

---



링크 삽입 시 주의 할것.인터렉티브 요소(링크)는 라벨 밖에 두어서 사용성과 접근성을 해치지 않게 한다.

```html
  <!-- good example - link outside label means checkbox activation area includes the checkbox and all the label text -->
  <label><input type=checkbox name=tac>I agree to the terms and conditions</label>
(read <a href="tandc.html">Terms and Conditions</a>)
```

---

폼 예시들 

```html
<fieldset>
  <legend>Destination</legend>
  <p><label>Airport: <input type=text name=to list=airports></label></p>
  <p><label>Name: <input type=text></label></p>
</fieldset>
<datalist id=airports>
  <option value=ATL label="Atlanta">
  <option value=MEM label="Memphis">
  <option value=LHR label="London Heathrow">
  <option value=LAX label="Los Angeles">
  <option value=FRA label="Frankfurt">
</datalist>
```



```html
<fieldset>
  <legend>Mail Account</legend>
  <p><label>Name <input type="text" name="fullname" placeholder="Elon Musk"></label></p>
  <p><label>Address <input type="email" name="address" placeholder="musk@spacex.com"></label></p>
  <p><label>Password <input type="password" name="password"></label></p>
  <p><label>Description: <input type="text" name="desc" placeholder="My Email Account"></label></p>
</fieldset>

```


---