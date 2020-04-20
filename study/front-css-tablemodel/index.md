---

layout: post
comments : true
title: 'FrontEnd CSS Table Model'
subtitle: 'CSS 테이블 모델'
date: 2020-04-21
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 90

---
> table 모델

<br>

- display: table;
- table의 레이아웃
  - 외부 레이아웃은 블록과 유사
  - width 설정 가능
    - 적용하지 않은 내용물(table-cell)들의 너비만큼 영역을 가진다(Auto)
  - height 설정 가능
    - 적용하지 않은 내용물(table-row)들의 높이만큼 영역을 가진다(Auto)
  - padding 설정 가능
    - table의 테두리와 table-cell들의 테두리 사이 공간이 넓어짐
  - margin 설정 가능
    - table의 외부여백
  - tr
    - tr 태그는 padding, margin 둘 다 적용해도 변화가 없다
    - tr 태그는 width는 적용 안되고 Height는 적용된다.
  - td, th
    - td, th 태그는 padding 적용 가능, margin은 적용 안된다.
    - td, th 태그는 width, height 둘 다 적용된다.
  - table
    - table-cell(td, th)에 각각 테두리가 존재한다.
    - tr 에는 테두리가 없다.
  - border-collapse 속성을 설정할 수 있다.
    - border-collapse: separate;
    - border-collapse: collapse;


<br><br>