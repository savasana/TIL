## number to string, string to number

자바스크립트에서 숫자를 문자로, 문자를 숫자로 바꾸는 여러가지 방법들을 알아보자



#### convert a string to a number

- `num = Number(str)`    // Number 생성자 사용
- `num = parseInt(str)`  // base에만 사용할것을 권장
- `num = + str`          // unary operators 가장 간편
- `num = str / 1`
- `num = str * 1`



#### convert a number to a string

- `str = num.toString();`   // null, undefined일때는 제대로 작동하지 않는다
- `str = String(num)`       // 그다지 추천하지 않는다 (by 쌤)
- `str = num + '';`         // 빈 스트링 더해준다 - 가장 간편

