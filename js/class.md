### Class

class in JS

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

class Square extends Polygon {
  constructor(length) {
    super(length, length);
    this.name = 'Square';
  }
}
```

class is TS

```js
class Polygon {

}
```