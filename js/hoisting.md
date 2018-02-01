###  Hoisting

- variable declarations and variable assignment happens at different time
- variables are belonging to their enclosing function
- function declaration *hoist*
- function expression doesn't *hoist*


How  `var ` keywords work
1. variable is added at compile time to the enclosing lexical scope
2. at runtime, when that scope starts, that variables get initialized to their undefined value.


How `let` keywords work
1. add declaration to their enclosing lexical environment scope
2. do not initialize them at the beginning of the scope / only get initialized to  the undefined value at the presence of the let keyword


![](images/Screen%20Shot%202018-02-01%20at%2021.54.30.png)



