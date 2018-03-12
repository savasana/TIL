### Destructuring
```js
let person = {
  name: {
    first: 'yohan',
    last: 'song'
  },
  language: {
    backend: {
      python: {
        experience: '3yrs',
        frameworks: 'django'
      }
    }
  }
}

let {name: { first }, language: { backend: serverSkills }} = person;
// console.log(`${first} - ${Object.keys(serverSkills)}`);
console.log(nop); // yohan
console.log(serverSkills); // {python: {experience: '3yrs', frameworks: 'django'}}

let { name: {foo} } = { name: {foo : 'oh', boo: 'da'} };
console.log(foo); // 'oh'
```


### Rest and Spread

```js
//Rest ... (and the rest go here!) 
// Left hand side!!
let data = { x: 1, y: 2, z: 3};
let { x, ...others } = data;
console.log(others); // {y:2, z:3}

//Spread
// Right hand side!
let value = { ...others, a: 100, b: 200};
console.log(value) // {y:2, z:3, a:100, b:200}
```