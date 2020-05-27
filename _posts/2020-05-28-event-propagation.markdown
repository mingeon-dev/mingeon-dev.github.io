---
layout: post
title: "[JavaScript] 이벤트 전파"
date: 2020-05-28 00:00:00 +0900
categories: JavaScript
---

이벤트 버블링, 이벤트 캡쳐링, event.stopPropagation()과 event.preventDefault(), 이벤트 위임

---

### 이벤트 버블링

- 이벤트가 발생했을 때 상위 요소로 전파되는 것

### 이벤트 캡쳐링

- 버블링과 반대로 하위로 전파되는 것

```javascript
// 세번째 인자 true로 설정할 경우 캡쳐링 동작
target.addEventListener(type, listener[, useCapture]);
```

### event.stopPropagation()과 event.preventDefault()

- event.stopPropagation(): 이벤트 캡쳐링과 버블링을 통한 전파를 막음
- event.preventDefault(): 이벤트 전파를 막지 않고 이벤트를 취소함 (예: \<a\> 태그 클릭 시 페이지 이동을 막음)

### 이벤트 위임

- 최상위 노드가 하위 노드들의 이벤트를 처리하도록 하는 것
- 이벤트 핸들러 관리가 쉬우며 동적으로 노드를 추가할 경우 처리가 용이함
- 이벤트 핸들러 개수를 줄임으로써 메모리 사용량 감소

### 참고 자료

- [이벤트 버블링, 이벤트 캡처 그리고 이벤트 위임까지 \| Captain Pangyo](https://joshua1988.github.io/web-development/javascript/event-propagation-delegation/)
- [EventTarget.addEventListener() \| MDN](https://developer.mozilla.org/ko/docs/Web/API/EventTarget/addEventListener)
