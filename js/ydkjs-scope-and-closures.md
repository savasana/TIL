## You Don’t Know JS : Scope & Closures


### Scope

#### compiled-language process
1. Tokenizing / Lexing : breaking into meaningful chunks - tokens
`var a = 2;` -> `var` , `a` , `=`, `;`

2. Parsing : taking a stream of tokens and turning it into a tree of nested elements. -> represent the grammatical structure of the program. *AST (Abstract Syntax Tree)*

```js
var a  = 2;
```

`var` : VariableDeclaration
`a` : Identifier (child node of VariableDeclaration)
`=` : AssignmentExpression
`2` :  NumericLiteral (child node of AssignmentExpression)

3. Code-Generation : taking an AST and turning into executable code.

---


Scope: collects and maintains a look-up list of all the declared identifiers(variables) and enforces a strict set of rules as to how these are accessible to currently executing code.

---

#### how compiler will proceed
`var a = 2;`
1. compiler declares a variable 
2. when executing, Engine looks up the variable in Scope and assigns to it.

#### compiler speak

**LHS** look-up : purpose of assigning to the variable
**RHS** look-up : purpose of retrieving its value

---


# chapter 2 : Lexical Scope
lexical scope is scope that is defined at sexing time. In other words, lexical scope is where variables and blocks of scope are authored, by you, at write time, and thus is set in stone by the lever processes your code.



