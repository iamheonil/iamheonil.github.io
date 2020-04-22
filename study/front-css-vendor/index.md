---

layout: post
comments : true
title: 'FrontEnd CSS Vendor Prefix'
subtitle: 'CSS 시맨틱 벤더 프리픽스'
date: 2020-04-22
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 94

---

> CSS 벤더 프리픽스

<br>

- CSS3 스타일 속성 앞에 붙이는 브라우저별 접두어
- 브라우저마다 접두어가 다르다
- CSS3를 반영한 브라우저 또는 해당 브라우저의 버전에 따라서 CSS3 스타일 속성을 테스트 하고 그에 따른 피드백을 제공하기 위해 사용된다.
- 표준적으로 CSS3가 적용되기 전에 브라우저마다 자체적으로 테스트나 개발을 위해 미리 적용된 속성에 접두어를 붙여서 사용할 수 있게 제공된 것들

<br>

- 프리픽스의 종류
  - -webkit-
    - 크롬, 사파리
  - -o-
    - 오페라
  - -ms-
    - 윈도우 인터넷 익스플로러
  - -moz
    - 파이어폭스
- ** 접두어를 적용한 CSS3 속성을 먼저 작성하고 접두어를 제거한 표준속성을 마지막에 작성한다.
  - 이전 버전의 속성보다 나중에 개발된 표준속성이 반영되도록 배치한 것
    
    
<br><br>