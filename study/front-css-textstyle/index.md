---

layout: post
comments : true
title: 'FrontEnd CSS Text Style'
subtitle: 'HTML/CSS에서 쓰이는 Text Style'
date: 2020-04-22
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 95

---

> CSS 텍스트 스타일

<br>

- font-size: 글자크기

  - em, px 를 주로 사용한다

- color: 글자색상

  - 색상 단위로 적용한다.

- font-style: 글씨체

  - Normal, Italic(이탤릭), Oblique(기울임)
  - Normal, Italic 을 가장 많이 사용한다.

- font-weight: 굵기

  - Normal, Bold, Bolder, Lighter
  - 100~900(숫자가 커질수록 굵어진다, 100단위로 설정한다.)
  - 100~300 Lighter
  - 400~500 Normal
  - 600~700 Bold
  - 800~900 Bolder

- font-variant: 글자 변형(다양성), 대소문자 글자 스타일

  - small-caps : 소문자를 작은 대문자로 표현

  - Normal

- text-align: 텍스트 정렬

  - left, right, center, justify
  - justify - 양쪽 정렬
  - 블록요소에 적용하는 스타일
  - 블록요소의 내부 컨텐츠를 정렬하는 역할(텍스트 또는 인라인요소)

- text-indent: 들여쓰기

  - text-indent: px;
  - px 단위를 사용한다.

- text-decoration: 꾸밈선

  - none - 없음
  - line-through - 취소선
  - underline - 밑줄
  - overline - 윗줄

- line-height: 줄 간격

  - inline 요소의 높이로 사용된다.
  - 1.35em이 기본 값
  - 주로 1.8em을 자주 사용하는 편이다.
  - font-size에 상대적인 간격을 가지도록 em으로 설정한다.
  - 글자가 들어가는 영역의 높이를 나타내며 글자 기준으로 위아래 공간이 생긴다.

<br>

> font-family, 서체

<br>

- 글꼴(== font)
- 서체를 지정하는 스타일 속성
- 글꼴에 영향을 준다.

<br>

- 서체의 종류
  - Serif - 돌출선이 들어간 서체
    - 한글 글꼴 : 바탕체, 궁서
    - 영어 글꼴 : Georgia, Times New Roman
  - Sans-Serif
    - Sans는 '없다'와 똑같은 뜻, 돌출선(Serif)이 없는 서체
    - 한글글꼴 : 돋움, 굴림, 고딕, 나눔 고딕, 맑음 고딕
    - 영어글꼴 : Arial, Helvetica
  - monospace
    - 고정 폭 서체, 오타 구분하기가 쉬워져서 코딩 시 많이 사용한다.
    - 대표 서체 : Consolas
  - cursive
    - 커브가 적용된 서체, 필기체를 나타낼 때 많이 사용한다
  - fantasy
    - 특이한 모영을 가진 서체, 개성있는 서체

<br>

### 서체를 CSS로 설정하는 방법

- font-famliy 는 글꼴을 명시하거나, 서체를 지정할 수 있다.
- font-family 의 설정값으로 설정한 서체나 글꼴을 여러 개 지정할 수 있다, 각 항목은 ','로 구분한다.
- 설정항목은 순서대로 웹페이지에서 반응한다.
- font-family: "돋움", Dotum, "굴림", Gulim, Arial, Helvetica, sans-serif;

<br><br>