---

layout: post
comments : true
title: 'FrontEnd CSS Inline Model'
subtitle: 'CSS 인라인 모델'
date: 2020-04-18
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 88

---

> inline 모델

<br>

- block 모델 요소의 내부 컨텐츠로 표현되는 요소
- 컨텐츠(내용물)만큼만 영역을 차지한다
- 컨텐츠가 부모 요소의 너비를 초과하면 새 행으로 줄바꿈한다.
- border를 설정하면 border도 같이 줄바꿈이 되므로 테두리가 깨진 것처럼 보일 수 있다.
- 인라인 요소에 border를 설정할 때에는 반드시 화면에 적용된 상황을 확인할 것
- 인라인 요소끼리는 같은 줄에 여러 개 배치할 수 있다.

<br>

- 자체 레이아웃
  - width, height : 속성이 적용되지 않는다. 내용물에 맞춰 컨텐츠 영역의 크기가 결정된다.
  - margin : left, right 만 적용되고 top, bottom 은 적용되지 않는다, 서로 만나면 겹쳐지지 않고 밀어낸다.
  - line-height : 줄 간격(줄 높이) 속성, 텍스트가 들어갈 수 있는 공간의 높이를 설정하는 속성, 인라인 요소의 높이를 결정할 수 있다. margin-top, margin-bottom 대신 활용한다.

<br><br>