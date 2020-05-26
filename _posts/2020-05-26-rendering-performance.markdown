---
layout: post
title: "[JavaScript] 렌더링 성능"
date: 2020-05-26 00:00:00 +0900
categories: JavaScript
---

렌더링 과정, 리플로우, 리페인트, 합성

---

### 렌더링 과정

![전체 픽셀 파이프라인](/assets/images/pixel-pipeline.jpg)

- 자바스크립트: jQuery의 animate 함수, 데이터 집합 정렬 또는 페이지에 DOM 요소 추가 등 시각적 변화를 일으키는 작업을 처리
- 스타일 계산: selector에 따라 어떤 CSS 규칙을 어떤 요소에 적용할지 계산
- 레이아웃: 화면에서 얼마의 공간을 차지하고 어디에 배치되는지 계산
- 페인트: 텍스트, 색, 이미지, 경계 및 그림자 등 요소의 모든 시각적 부분을 그리는 작업
- 합성: 페이지의 여러 부분이 잠재적으로 여러 레이어로 그려졌기 때문에 정확한 순서로 화면에 조합

### 리플로우

- 레이아웃 너비, 높이, 왼쪽 또는 상단 위치 등 요소의 기하학적 형태에 영향을 주는 '레이아웃' 속성을 변경하면 브라우저가 다른 모든 요소를 확인하고 페이지에 대해 리플로우(레이아웃, 페인트, 합성 과정) 수행
- height, width, left, top, font-size, line-height 등

### 리페인트

- 배경 이미지, 텍스트 색상 또는 그림자 등의 '페인트' 속성을 변경하면 레이아웃을 건너뛰고 리페인트(페인트, 합성 과정) 수행
- color, visibility, text-decoration 등

### 합성 (Composite)

- 레이아웃과 페인트가 필요 없는 속성을 변경하면 브라우저가 합성 과정만 수행
- transforms, opacity 등

### 참고 자료

- [렌더링 성능 \| Google Developers](https://developers.google.com/web/fundamentals/performance/rendering?hl=ko)
- [성능 최적화 \| TOAST UI](https://ui.toast.com/fe-guide/ko_PERFORMANCE/)
