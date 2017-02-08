# ECMAScript 2015에서 새로운 문법 익히기


[참조](https://github.com/DrkSephy/es6-cheatsheet)

ES5 VS ES6

Class 
```javascript

```

Template Literals
```javascript

```

Arrow Functions

String.includes
```javascript
var foo = "Hello world"
foo.includes("Hello");
// true
```

String.reapeat
```javascript
var foo = "world"
foo.repeat(4);
// worldworldworldworld
```

[비구조화 할당](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

```javascript
var obj = {foo: 2, boo: 3};
var {foo, boo} = obj

[a, b, ...rest] = [1, 2, 3, 4, 5];
// a = 1, b = 2, ...rest = 3,4,5

function fooFn({a}) {
    console.log(a)
}
var obj = {a: 2};
fooFn(obj);
// 2
```
