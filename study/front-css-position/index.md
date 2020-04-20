---

layout: post
comments : true
title: 'FrontEnd CSS Position의 속성'
subtitle: 'CSS Position 속성'
date: 2020-04-21
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 91

---

> Position 속성

<br>

- Layout 배치 속성
- 요소의 위치에 대한 설정 속성
- position을 설정하더라도 기본 display 속성은 유지된다
  - static
    - 기본 위치
    - 해당 요소가 위치했어야하는 곳에 자연스럽게 배치된다.
  - absolute
    - 절대 위치
    - 기준위치는 Position 속성을 받은 부모요소의 레이아웃
    - 상하좌우 네 벽면을 기준으로 삼는다.
    - 부모요소가 position 속성이 아니라면 첫 화면을 기준으로 위치가 지정된다.
  - relative
    - 상대 위치
    - 기존에 자기가 표현되어야하는 위치의 좌측상단지점을 기준으로 이동
    - 기존 해당 요소가 존재했어야하는 공간이 유지된다
    - 다른 태그가 해당 공간을 사용하지 않고 비워둔다, 상대 위치 박스는 이동시키지 않고 사용한다
    - absolute박스의 부모 요소가 된다.
  - fixed
    - 고정 위치를 지정한다
    - 보고있는 화면의 상하좌우 벽면을 기준으로 삼고 이동한다.
    - 스크롤을 따라온다.
  - top, bottom, left, right 속성을 이용하여 요소의 위치를 반영한다
  - 이동되는 위치의 기준점이 position의 속성마다 다르다
  - relative 를 부모요소로 두고 absolute를 자식요소로 넣어서 많이 사용한다.
  - position: absolute; 가 부여되면 기존 HTML 문서 구조를 무시하고 절대위치를 설정하게 된다.
    - -> 브라우저의 첫 화면을 기준으로 삼는다.
    - relative를 부모요소로 두면 absolute의 절대 위치기준점이 부모요소로 설정된다.


<br><br>