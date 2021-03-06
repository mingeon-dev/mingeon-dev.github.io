---
layout: post
title: "[JavaScript] 실행 컨텍스트 및 this"
date: 2020-05-21 00:00:00 +0900
categories: JavaScript
---

실행 컨텍스트, 호이스팅, 스코프, var, let, const, this

---

### 실행 컨텍스트

- 실행할 코드에 제공할 환경 정보들을 모아놓은 객체

### 호이스팅

- 호이스팅은 코드 해석을 좀 더 수월하게 하기 위해 매개변수명, 변수의 식별자, 선언한 함수의 함수명 등의 수집 과정을 추상화한 개념
- 실행 컨텍스트가 관여하는 코드 집단의 최상단으로 이들을 '끌어올린다'고 해석하는 것
- 변수는 선언부만 끌어올림
- 함수 선언문(`function a() { ... }`)은 전체를 끌어올리며, 함수 표현식(`var a = function() { ... }`)은 선언부만 끌어올림

### 스코프

- 스코프는 변수의 유효 범위
- 코드 상에서 어떤 변수에 접근하려고 하면 현재 컨텍스트의 내부 스코프에서 외부 스코프 순으로 탐색

### var, let, const

- var는 함수 단위 스코프, let과 const는 블록 단위 스코프를 가짐
- var는 재선언, 재할당 가능
- let은 재선언 불가능하지만 재할당 가능
- const는 재선언, 재할당 불가능
- let과 const는 호이스팅이 되지 않는 것 같지만, 실제로는 호이스팅이 되며 다만 호이스팅 시 초기화되지 않아 'is not defined' 에러 발생

### this

- this에는 실행 컨텍스트를 활성화하는 당시에 지정된 this가 저장됨
- 지정되지 않은 경우 전역 객체가 저장됨
- 메서드로서 호출한 경우 this는 메서드 호출 주체(메서드 앞의 객체)를 참조
- 함수로 호출한 경우 this는 전역 객체를 참조
- 콜백 함수 내부에서의 this는 해당 콜백 함수의 제어권을 넘겨받은 함수가 정의한 바에 따르며 정의하지 않은 경우 전역 객체 참조
- 생성자 함수에서의 this는 생성될 인스턴스 참조
- 화살표 함수 내부에서는 this가 없으며 접근할 경우 스코프 체인상 가장 가까운 this에 접근하게 됨

### 참고 자료

- [var, let, const 특징 및 호이스팅 \| sjk5766](https://medium.com/sjk5766/var-let-const-%ED%8A%B9%EC%A7%95-%EB%B0%8F-scope-335a078cec04)
- 정재남, 코어 자바스크립트, 위키북스(2019)
