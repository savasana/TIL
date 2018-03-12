### Class

### class in JS
- 멤버로 메서드만 올 수 있다.
- 멤버변수들은 메서드 안에.

```js
class Polygon {
  constructor(height, width) {
    this.name = 'Polygon';
    this.height = height;
    this.width = width;
  }
  area() {
    return this.height * this.width;
  }
}

```

```js
var pol = new Polygon(5, 3);
pol.area();
```

### class is TS
- 멤버로 변수, 메서드 다 올 수 있다.
- 디폴트가 public

```ts
class Polygon {
  width: number;
  height: number;
  constructor(width: number, height: number) {
    this.width = width;
    this.height = height;
  }
  area() {
    return this.width * this.height;
  }
}
```