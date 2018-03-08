## Regular Expression

- 정규표현식, 패턴 매칭 언어로 다양한 프로그래밍 언어에서 사용가능
- str.split
- str.match
- str.replace
- re.test(str)
- re.exec(str)

---

### 기본 사용법

- `var regex = /regex/;` literal로 생성
- `var regex = new RegExp('regex');` constructor function으로 생성
- 정규표현식이 고정값일 경우 literal 사용 (perfomance가 더 좋다)
- 생성자 함수로 만든경우 runtime compilation 이므로 변하는 값을때 사용한다. 정해진 패턴이 없고 input에 따라 달라질 경우.

### 작성방법

- `/PATTERN/FLAGS/`
- flags와 meta character써서 원하는 값 찾는다.

```js
'one two three'.replace(/one/, '1');
// one과 정확히 일치하는 값을 찾는다
// '1 two three'
'1 two three'.replace(/\d+/, 'NUMBER');
// NUMBER two three
```


---

## flags

- `/i` case insensitive
- `/g` match all occurences(global)
- `/m` treat string as multiple lines
- `/s` treat string as a single line

---

## meta characters

- `.` for any character 모든 아무 캐릭터

**quantifiers** 갯수 선택
- `/el?/` 
- `*` zero or more times
- `+` one or more times


- `[]` character class
- `^` anchor atthe beginning
- `$` anchor to the end
- `(a|b)` match a or b
- `()` capture group
- `(?:)` non capture group
- `\d` digit `[0-9]`
- `\w` word `[A-Za-z0-9_]`
- `\s` whitespace `[ \t\r\n\f]`

```js
str = 'hello beep boob';
str.replace(/b..p/, 'WHATEVER');
// b와 p사이의 아무 캐릭터(..)/
// global flag 없으므로 첫번째 매칭 결과 사용
'hello WHATEVER boop'
 
str.replace(/b..p/g, 'WHATEVER');
// g 글로벌 - 모든 결과 선택
'hello WHATEVER WHATEVER'
```