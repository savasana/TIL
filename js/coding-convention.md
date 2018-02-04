## Coding convention

###  what is coding convention?

코딩컨벤션이란 프로그래밍 언어를 위한 가이드 라인이라고 할 수 있다.  프로그래밍 세상에서 원작자에 의해 계속 유지되는 코드는 거의 없다. 대부분의 프로그램은 수많은 사람들의 손을 거친다. 따라서 가독성과 유지보수 관점에서 코딩컨벤션을 가지고 따르는것이 중요하다. 

특히나 처음 배우는 단계에서는 이런 부분을 아직은 필요 없다고 느끼고 무시하기 쉬운데 작은 부분을 어떻게 하는지에 따라 전체가 달려있다고 생각한다. 덤벙대고 무심하고 대충대충을 좋아하는 나에게 특히나 어렵게 느껴지는 부분이라서 더욱 중요하게 생각하고 노력해야겠다.

> set of guidelines for a specific programming language that recommend programming style, practices, and methods for each aspect of a program written in that language.
> [Coding conventions - Wikipedia](https://en.wikipedia.org/wiki/Coding_conventions)

---

### Douglas Crockfords says…

*frontend master에서 더글라스 아저씨가 강조한 writing style 관련해 새겨두면 좋을 내용들*

- Programs must communicate clearly to people.
- Confusion must be avoided.
- Always use `===` 
- Make your programs look like what they do.
- Write in the language you are writing in.
- `++`   occurs ambiguity. use   `x += 1` instead.
- Clean code is easier to reason about.

---
### Style guides

**잘 정리된 스타일 가이드를 찾을 수 있는 링크 - Airbnb가 가장 엄격하기로 유명하다**

- [GitHub - rwaldron/idiomatic.js: Principles of Writing Consistent, Idiomatic JavaScript](https://github.com/rwaldron/idiomatic.js)
- [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- [Code Conventions for the JavaScript Programming Language](https://crockford.com/javascript/code.html)

---

### Linting

**Style guide를 바로바로 체크해주는 에디터 확장 프로그램들**

- [ESLint - Pluggable JavaScript linter](https://eslint.org/) 
- [About JSHint](http://jshint.com/about/)
- [JSLint: Help](http://www.jslint.com/help.html)


ESLint를 사용중인데 처음에 configuration 과정을 거쳐야 하는 불편함을 빼고는 사용자 정의 룰을 입력가능하고 다양한 확장기능 또한 가능해 훌륭해 보인다.






