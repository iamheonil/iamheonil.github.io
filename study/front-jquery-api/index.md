---

layout: post
comments : true
title: 'FrontEnd jQuery API'
subtitle: 'jQuery API'
date: 2020-05-07
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 111

---

> jQuery API

<br>



- jQuery Core
  - jQuery 문법이 적용되었음을 알리는 키워드
    - jQuery
    - $
    - ex) document.getElementById("idname") 와 같은코드를 jQuery("#idname"), $("#idname") 으로 사용할 수 있다.
  - jQuery Core 키워드는 변수에 저장하여 사용할 수 있다.
    - var J = jQuery; --> J("#idname")

<br>

- jQuery 스타일의 DOM 객체 이용 코드
  - $(document).ready(function() { } ) == window.onload = function() { }

<br>

- jQuery 노드객체 찾기
  - $("CSS셀렉터")
  - $(jsDOM객체)
    - 순수 JS API를 적용할 수 있는 객체를 jsDOM객체
    - jQuery API를 적용할 수 있는 객체를 jqDOM객체
    - 순수 JS API를 사용할 수 있는 DOM 객체와 jQuery API를 사용할 수 있는 DOM 객체의 형식이 다르다.

<br><br>