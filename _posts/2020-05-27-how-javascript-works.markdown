---
layout: post
title: "[JavaScript] 자바스크립트 동작 원리"
date: 2020-05-27 00:00:00 +0900
categories: JavaScript
---

자바스크립트 엔진, 런타임, 콜 스택, 동시성과 이벤트 루프, 마이크로 태스크

---

![자바스크립트 런타임](/assets/images/javascript-runtime.png)

### 자바스크립트 엔진

- 자바스크립트 엔진의 주요 두 구성 요소는 메모리 힙과 콜 스택
- 메모리 힙은 메모리 할당이 이루어지는 곳
- 콜 스택은 코드가 실행되면서 스택이 쌓이는 곳

### 런타임

- Web APIs는 자바스크립트 엔진이 아닌 브라우저에서 제공하는 API

### 콜 스택

- 자바스크립트는 기본적으로 싱글 쓰레드이기 때문에 콜 스택이 하나
- 함수를 실행하면 해당 함수는 콜 스택의 가장 상단에 위치
- 함수의 실행이 끝날 때 해당 함수를 콜 스택에서 제거
- 무한 재귀 등으로 인해 콜 스택의 최대 허용치를 넘게 되면 'Maximum call stack size exceeded' 에러 발생

### 동시성(Concurrency)과 이벤트 루프

- 이벤트 루프는 콜 스택과 콜백 큐를 감시하며, 콜 스택이 비어 있으면 큐에서 이벤트를 꺼내 콜 스택에 넣어 실행
- 콜 스택 처리 시간이 오래 걸릴 경우 브라우저가 응답하지 않는 상태 발생하며 이는 비동기 콜백을 통해 해결

### 마이크로 태스크(Microtask)

- 현재 실행되고 있는 작업 바로 다음에 실행되며, 일반 태스크보다 높은 우선 순위를 가짐 (모든 마이크로 태스크가 실행된 후에 일반 태스크 실행)
- observer callback이나 promise callblack이 대표적인 마이크로 태스크

### 참고 자료

- [자바스크립트의 동작원리: 엔진, 런타임, 호출 스택 \| Captain Pangyo](https://joshua1988.github.io/web-development/translation/javascript/how-js-works-inside-engine/)
- [Don’t block the event loop! 매끄러운 경험을 위한 JavaScript 비동기 처리 \| LINE Engineering](https://engineering.linecorp.com/ko/blog/dont-block-the-event-loop/)
- [[번역] Tasks, microtasks, queues and schedules \| bono's blog](https://blueshw.github.io/2018/01/28/tasks-microtasks-queues-and-schedules/)
