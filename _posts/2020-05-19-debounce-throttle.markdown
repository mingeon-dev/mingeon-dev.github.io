---
layout: post
title: "[JavaScript] 디바운스와 스로틀"
date: 2020-05-19 00:00:00 +0900
categories: JavaScript
---

디바운스, 스로틀, 예제 코드

---

### 디바운스(Debounce)

- 연달아 호출되는 함수의 마지막만 호출하도록 하는 것
- window resize, 검색 등과 같이 연속된 이벤트가 발생하는 경우 사용

```javascript
var timer;
// 이벤트 리스너 내부
if (timer) {
  clearTimeout(timer);
}
timer = setTimeout(function () {
  // 로직
}, 200);
```

### 스로틀(Throttle)

- 함수가 호출된 후 일정 시간이 지나기 전에 다시 호출되지 않도록 하는 것
- 스크롤 시 주로 사용
- Debounce와 차이점: Throttle은 적어도 몇 초마다 정기적인 실행을 보장한다. Debounce는 아무리 이벤트가 많이 발생해도 마지막 이벤트만 실행한다.

```javascript
var timer;
// 이벤트 리스너 내부
if (!timer) {
  timer = setTimeout(function () {
    timer = null;
    // 로직
  }, 200);
}
```

### 참고 자료

- [쓰로틀링과 디바운싱 \| ZeroCho Blog](https://www.zerocho.com/category/JavaScript/post/59a8e9cb15ac0000182794fa)
- [디바운스(Debounce)와 스로틀(Throttle) 그리고 차이점 \| Web Club](https://webclub.tistory.com/607)
