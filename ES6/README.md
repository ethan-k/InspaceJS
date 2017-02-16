# ECMAScript 2015에서 새로운 문법 익히기


[참조](https://github.com/DrkSephy/es6-cheatsheet)

## ES5 VS ES6

### Class 
```javascript

```

### Template Literals
```javascript

```

### 화살표 함수 
```javascript
var arr = [
  "foo",
  "boo",
  "Lithium",
  "Beryl­lium"
];
// ES6 이전 방식
var a2 = arr.map(function(s){ return s.length });

// ES6 이후 방식
var a3 = a.map( s => s.length );

// 지정된 값만을 리런
() => 2 

```

** 화살표 함수를 사용할때 주의할점은 함수내의 this가 함수에 바인딩되지 않습니다
즉 자기 자신 고유의 스코프를 가지지 않습니다

```javascript
function Animal() {
  this.legs = 4;
  function grow() {
      this.legs = 3;
  }
}


```



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
