---

layout: post
comments : true
title: 'FrontEnd CSS Inline Block Model'
subtitle: 'CSS 인라인 블록 모델'
date: 2020-04-21
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 89

---

> Inline - Block 모델

<br>

- Inline 모델과 Block 모델의 표현방식이 섞인 것
- 내부 동작은 블록모델
  - 요소의 자체 레이아웃
  - width, height, border, margin, padding 모두 적용 가능
- 외부 동작은 인라인모델
  - 외부 요소와의 관계에 대한 레이아웃
  - 블록모델처럼 한 줄을 다 차지하지 않는다.
  - 인라인요소처럼 한 줄에 여러 요소 배치가 가능하다.

<br>

- 자체 레이아웃
  - width, height 설정 가능
    - 부묘요소에 맞추려면 width: 100% 로 설정
    - 내용물 크기에 맞추려면 height: auto 값으로 설정
  - margin-top, margin-bottom 설정 가능
  - margin-left, margin-right 설정 가능
    - 외부 요소와의 간격으로 사용되며 인라인모델처럼 동작한다

<br><br>