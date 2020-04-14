---

layout: post
comments : true
title: 'FrontEnd CSS 크기 단위'
subtitle: 'CSS 설계시 사용되는 단위들에 대하여'
date: 2020-04-15
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 83

---

> CSS 크기 단위

<br>

- 고정 크기 단위
  - 주변요소(부모요소)의 크기에 영향받지않고 일정한 크기를 유지하는 단위
    - px : 픽셀, 화소 단위, 정확한 크기나 위치를 설정할 때 사용한다.
    - in : 인치, 설정되어있느 수치를 따라간다(픽셀 수로 설정되어 있다. 1in = 96px)
    - pc : 파이카라고 한다, 1/6in == 16px
    - pt : 포인트라고 한다, 1/12pc == 1/72in
    - cm : 센티미터, 2.54cm == 1in
    - mm : 밀리미터, 1/10cm
  - 고정 단위라고하지만 현실의 크기와는 다르다.

<br>

- 가변 크기 단위
  - 주변요소(부모요소)에 비례한 상대적인 크기를 지정하는 단위
    - % : 퍼센트, 태그 요소가 들어갈 수 있는 공간에서의 비율(부모 요소의 크기에 영향을 받는다.)
    - em : 엘리먼트의 약자(단순히 em이라고 읽는다) 부모요소에서 지정한 크기의 배율로 설정하는 단위
      - 1em == 100%, 1.5em == 150%
      - font-size(글자크기), Line-height(줄간격) 에서 많이 사용된다.
    - rem : Root EM, 최상위 부모요소(html태그)의 크기의 배율로 설정하는 단위
      - 최상위 부모요소인 html 태그의 글자크기는 16px 이다.
    - ex : Element X-height, 현재 폰트의 소문자 'x'의 배율

<br><br>