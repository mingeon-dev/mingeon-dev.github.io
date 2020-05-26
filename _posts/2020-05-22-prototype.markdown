---
layout: post
title: "[JavaScript] 프로토타입"
date: 2020-05-22 00:00:00 +0900
categories: JavaScript
---

프로토타입, 프로토타입 체이닝

---

### 프로토타입

- 어떤 생성자 함수를 new 연산자와 함께 호출하면 Constructor에서 정의된 내용을 바탕으로 새로운 인스턴스가 생성되는데, 이 인스턴스는 \_\_proto\_\_라는 Constructor의 prototype 프로퍼티를 참조하는 프로퍼티가 자동 부여됨
- \_\_proto\_\_는 생략 가능한 속성이라서 인스턴스는 Constructor.prototype의 메서드를 마치 자신의 메서드인 것처럼 호출할 수 있음

### 프로토타입 체이닝

- \_\_proto\_\_ 방향을 계속 찾아가면 최종적으로는 Object.prototype에 당도함
- 이런식으로 \_\_proto\_\_ 안에 다시 \_\_proto\_\_를 찾아가는 과정을 프로토타입 체이닝이라고 하며, 이 프로토타입 체이닝을 통해 각 프로토타입 메서드를 자신의 것처럼 호출할 수 있음
- Object.prototype에는 모든 데이터 타입에서 사용할 수 있는 범용적인 메서드만이 존재하며, 객체 전용 메서드는 여느 데이터 타입과 달리 Object 생성자 함수에 스태틱하게 담김

### 참고 자료

- [상속과 프로토타입 \| MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain)
- 정재남, 코어 자바스크립트, 위키북스(2019)
