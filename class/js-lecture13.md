### Promise

- 자바스크립트는 비동기 처리를 위해 콜백을 사용.
- callback hell이 발생, 에러처리가 안됨 -> promise가 생김

- 비동기 방식에서는 try, catch에러를 잡을 수 없다.


---


### Module


### export & import

- 파일별로 각각의 scope를 가진다.
- a 파일은 b 파일의 내용을 볼 수 없다 (vice versa)
- 공개하고 싶은 부분만 export해서 공개할 수 있다. 다른 파일도 import로 참조가능


---

### babel
[babel installation](https://babeljs.io/docs/setup/#installation)
바벨 설치하기
- 작업폴더로 이동
- `npm init -y` : 기본 y옵션으로 설정
- `node_modules`폴더는, 설치한 모듈이 돌아가는데 필요한 dependencies들이 들어있음

```
$ mkdir 작업폴더 && cd 작업폴더
$ npm init -y
$ npm install babel-cli --save-dev

// root에 .babelrc 파일 생성
$ npm install babel-preset-env --save-dev

```


```js
{
  "name": "babel-project",
  "version": "1.0.0",
  <!-- name, version 은 필수  -->
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "babel-cli": "^6.26.0"
  }
}
```



`devDependencies` : 개발할때만 필요한 것들은 여기에 `--save-dev` 이렇게 설치
`dependencies` : 개발뿐만 아니라 후에 업로드에도 필요할때 save dev안하고 바로 저장하면 됨.


### Webpack


- `$ npm install webpack webpack-cli --save-dev` webpack설치

- `package.json`수정한다
    ```js
    "scripts": {
        "build": "webpack -w" //webpack
      }
    ```

- `$ npm install babel-loader --save-dev`
- `webpack.config.js`만든다

```js
const path = require('path');

module.exports = {
  entry: {  // 엔트리포인트, 진입점 , 가장 먼저 실행되는 파일
    entry: './src/js/entry.js'
  },
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist/js')
  },
  module: {
    rules: [{
      test: /\.js$/,    // 모든 js파일을 대상으로
      include: [
        path.resolve(__dirname, 'src/js')
      ],
      exclude: /node_modules/,     // node_modules파일은 제외하고
      use: {
        loader: 'babel-loader',
        options: {
          presets: ['env']  // 이 설정을 사용해서
        }
      }
    }]
  },
  devtool: 'source-map',
  mode: 'development' // Webpack V4에서 추가
};
```
