---

layout: post
comments : true
title: 'FrontEnd CSS Box Model'
subtitle: 'CSS 박스모델'
date: 2020-04-18
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 87

---

> CSS 박스 모델

<br>

- 화면에 배치되는 태그 요소를 어떻게 표현할 것인지 설정하는 속성
- display 속성으로 설정한다
  - width, height
  - border
  - padding, margin
  - 위 다섯가지 속성이 박스 모델에 따라 표현되는 방법이 달라진다

<br>

- block 모델
  - 영역을 설정하고 공간을 차지하는 요소
  - 너비의 기본 설정이 부모요소의 크기만큼(100%) 되어있다.
  - 컨텐츠(내용)의 크기가 block 요소보다 커지면 넘치는 부분이 발생한다.
  - 컨텐츠가 넘친 부분에 대한 표현방법으로 Overflow 속성을 사용한다.

<br>

- 종결 block 요소
  - h1 ~ h6, p, caption, dt, address, blockquote 등등
  - 종결 블락요소는 다른 블락요소를 자식대그로 가질 수 없다
  - 인라인 요소만 컨텐츠로 포함할 수 있다.

<br>

- 자체 레이아웃
  - width, height 속성 적용가능, 기본 값은 auto
  - width - 부모요소의 너비만큼 (100%)
  - height - 내부 요소의 높이만큼(auto)
  - margin - 외부 요소와의 간격을 설정하는 속성(외부 여백), margin 영역에 서로 만날 때 밀어내지 않고 겹쳐진다. 음수로 지정하면 컨텐츠 영역이 겹쳐진다. width가 설정된 블락요소에 margin: 0 auto; 를 설정하면 외부정렬(가운데정렬)이 가능하다.(부모 요소의 가운데로 정렬되는 것)

<br>

- Overflow 속성
  - 블락 요소 내의 내용물이 컨텐츠 영역보다 커서 넘친 부분에 대한 표현 방법을 설정하는 속성
  - visible : 넘친 부분 보여주기
  - hidden : 넘친 부분 감추기(잘라내기)
  - scroll : 상하, 좌우 스크롤바 생성하기 
    - 상하 스크롤바 == 수직 스크롤바 == vscroll == vertical scroll
    - 좌우 스크롤바 == 수평 스크롤바 == hscroll == horizontal scroll
  - auto : 내용물이 넘친 방향에만 스크롤 생성하기
- overflow-x, overflow-y 의 통합 속성
  - overflow-x : 좌우방향(수평방향)에 대한 넘친부분 처리 속성
  - overflow-y : 상하방향(수직방향)에 대한 넘친부분 처리 속성
    - ex) overflow-x : scroll; overflow-y : hidden;

<br><br>