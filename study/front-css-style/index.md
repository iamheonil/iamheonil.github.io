---

layout: post
comments : true
title: 'FrontEnd CSS 스타일 적용 우선순위'
subtitle: ''
date: 2020-04-18
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 86

---

> CSS 스타일 적용 우선순위

<br>

+ 선택자 우선순위
  1. 아이디 선택자
  2. 클래스/속성/가상 선택자
  3. 태그 선택자
  4. 전체 선택자
+ 스타일 적용방법에 따른 우선순위
  1. !important
  2. 인라인
  3. 임베디드
  4. @import
  5. link
  6. link 태그 안에 적용된 @import(이건 적용하지 않는게 좋다.)
  7. 브라우저의 기본 스타일

<br><br>

> 레이아웃 흐름 속성(요소 배치)

<br>

- float
  - 요소를 배치하는 방향을 지정하는 속성
  - floating의 약자이다.
  - 레이아웃을 구성할 때 사용하는 속성이다.
  - 흐름 방향을 지정하는 속성값
    - left : 왼쪽
    - right : 오른쪽
    - none : float 하지 않음.
  - 이미지와 텍스트(p 태그)를 한 줄에 배치하기 위해 사용되는 속성, 이미지를 이동시킬 수 있도록(Flaoting할 수 있도록) 만들고 그 자리를 텍스트가 배치될 수 있게 만든다.
- clear
  - float 속성을 부여한 요소는 다음에 오는 요소에게 영향을 미친다
  - float 요소의 옆으로 배치되려고 한다
  - clear 속성을 부여햐면 float 속성을 무시하고 배치된다.
  - left - float: left; 무시(제거)
  - right - float: right; 무시(제거)
  - both - left, right 모두 무시
  - none - float의 영향을 허용한다.

<br><br>