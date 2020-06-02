---
layout: post
title: "[JavaScript] 불변성"
date: 2020-06-02 00:00:00 +0900
categories: JavaScript
---

불변성, Object.assign(), 전개 구문, 배열 내장 함수, 관련 라이브러리

---

### 불변성

- 기본형(Number, String, Boolean, Null, Undefined, Symbol)은 불변값이며, 참조형(Object)은 가변값 (참고: [데이터 타입](https://mingeon-dev.github.io/posts/data-type/))
- Object가 참조를 통해 공유되어 있다면 함께 변경되는 문제 발생
- 이를 해결하기 위해 Object가 생성된 이후 그 상태를 변경할 수 없는 "불변성"을 유지하는 것이 필요

### Object.assign()

- Object로부터 다른 Object로 속성을 복사할 때 사용
- 속성의 값만 복사하기 때문에 중첩된 Object의 깊은 복사는 되지 않음

```javascript
const obj = { a: 1 };
const copy = Object.assign({}, obj); // 불변성을 유지한 Object 생성
console.log(copy); // { a: 1 }
```

### 전개 구문

- 전개 구문(Spread syntax)을 통해 Object.assign()보다 짧은 문법으로 불변성 유지

```javascript
var obj1 = { foo: "bar", x: 42 };
var obj2 = { foo: "baz", y: 13 };
var clonedObj = { ...obj1 }; // Object { foo: "bar", x: 42 }
var mergedObj = { ...obj1, ...obj2 }; // Object { foo: "baz", x: 42, y: 13 }
```

### 배열 내장 함수

- [Array.prototype.map()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map), [Array.prototype.filter()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/filter), [Array.prototype.concat()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/concat) 등은 새로운 배열을 생성하여 반환하므로 불변성 유지

### 관련 라이브러리

- 위 방법들은 중첩된 Object의 깊은 복사를 위해 코드가 복잡해지고 관리가 어렵기 때문에 보통 라이브러리를 사용
- [immutable](https://immutable-js.github.io/immutable-js/)
- [immer](https://immerjs.github.io/immer/docs/introduction)

### 참고 자료

- 조 모건, 자바스크립트 코딩의 기술, 길벗(2019)
- [Immutability \| PoiemaWeb](https://poiemaweb.com/js-immutability)
- [Object.assign() \| MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
- [전개 구문 \| MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
