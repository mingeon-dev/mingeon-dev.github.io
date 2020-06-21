---
layout: post
title: "[JavaScript] Web Worker"
date: 2020-06-10 00:00:00 +0900
categories: JavaScript
---

Web Worker

---

### Web Worker

- 스크립트 실행을 메인 쓰레드가 아닌 백그라운드 쓰레드에서 실행할 수 있도록 해주는 기술
- 무거운 작업을 분리된 쓰레드에서 처리할 수 있으며, 이를 통해 메인 쓰레드(UI 쓰레드)는 멈춤, 속도 저하 없이 동작할 수 있음
- 직접 DOM이나 메인 쓰레드의 콘텍스트에 접근 할 수 없음

### 참고 자료

- [Web Workers API \| MDN](https://developer.mozilla.org/ko/docs/Web/API/Web_Workers_API)
- [Don’t block the event loop! 매끄러운 경험을 위한 JavaScript 비동기 처리 \| LINE Engineering](https://engineering.linecorp.com/ko/blog/dont-block-the-event-loop/)
