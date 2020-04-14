---

layout: post
comments : true
title: 'FrontEnd CSS LayOut'
subtitle: 'CSS 레이아웃의 기초'
date: 2020-04-15
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 84

---

> CSS 레이아웃

<br>

- 화면에 표현될 요소를 배치하는 작업
- 어떤 요소를 어디에 어떻게 배치할 것인가에 대한 전략
- 태그의 모양을 설정하고 배치될 위치, 다른 요소들과의 관계 등을 지정한다.

<br>

- 태그의 기본적인 영역(공간)의 크기
  - width : 컨텐츠 영역의 너비
  - height : 컨텐츠 영역의 높이
  - padding : 내부 여백
  - border : 테두리
  - margin : 외부 여백

<br>

- CSS 여백
  - 태그 요소를 감싸고 있는 투명한 공간
  - padding(내부여백), margin(외부여백) 으로 구성한다.
  - 내부여백, 외부여백 둘 다 top, right, bottom, left로 구성된다.
  - 설정 방법
    - padding과 margin 둘 다 설정 방법이 똑같다.
    - ex) margin 기준으로 작성하였으며 padding, margin 둘 다 크기단위(px)로 설정한다.
      - margin: all; : 상하좌우 전부 적용
      - margin-top, margin-bottom : 상, 하
      - margin-left, margin-right : 좌, 우
      - margin-top, margin-left 와 같이 상, 좌 적용 가능하고, 마찬가지로 하, 우도 적용 가능하다
      - 속성을 입력하지 않고 값을 쓰게 된다면 상 - 우 - 하 - 좌(시계방향) 순으로 크기가 변경된다.

<br>

- CSS 테두리
  - 태그의 컨텐츠 영역과 내부 여백을 감싸는 영역
  - 테두리까지 요소의 내부로 취급한다. (외부는 Margin 밖에 없다.)
  - 설정 방식
    - 옵션 : border-width, border-style, border-color 순으로 작성한다.
      - border-width : 테두리의 두께, 주로 px 단위를 이용하여 설정한다.
        - width 의 옵션 : thin(1px), thick(5px), medium(3px, 기본값)
      - border-style : 테두리 선의 모양
        - solid(실선), dotted(점), dashed(점선), double(두 줄), groove(안쪽 마루), ridge(바깥쪽 마루), inset(오목, 안쪽 그림자), outset(볼록, 바깥쪽 그림자), hidden(숨김)
      - border-color : 테두리의 색상
        - 색상 단위를 이용한 테두리 색상 지정
    - ex) border: 1px soild black; 
    - ex) border-width: 10px;
    - ex) border-style: groove;
    - ex) border-color: dodgerblue;

<br><br>