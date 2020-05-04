---

layout: post
comments : true
title: 'FrontEnd JavaScript Event 코드 작성 방법'
subtitle: 'JavaScript Event'
date: 2020-05-05
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 108

---

> JS Event 처리코드 작성(등록)하는 방법

<br>

- 이벤트(Event)가 발생하면 해당 이벤트에 알맞은 동작을 수행할 수 있도록 코드를 작성해둬야한다.

<br>

- 이벤트 처리코드 == 이벤트 핸들러(handler) == 이벤트 리스너(Event Listener)
  - 이벤트가 발생했을 때 그 상황에 맞춰 동작할 코드

<br>

1. HTML 태그의 이벤트 속성을 이용한 인라인 방식으로 등록하기
   - button onclick="alert('clicked')">
   - div onmousemove="console.log('moved')">
2. DOM을 이용한 이벤트 리스너 바인딩 - 1 (Event Attribute 사용)
   - button id="btnOk"> 라고 하면,
   - script 태그를 이용하여 btnOk.onclick = function() { } 와 같이 코드를 작성해준다.
   - btnOk.onmousemove = fn; / function fn() { console.log("마우스 움직임!") } 와 같이 함수를 불러오는것이 가능하다.
   - 
3. DOM을 이용한 이벤트 리스너 바인딩 - 2 (Event API 함수 사용
   - 이벤트발생객체.addEventListener("이벤트 이름", 콜백함수)
     - btnTest.addEventListener("click", function() {alert("Test"); });
   - 이벤트발생객체.removeEventListener("이벤트 이름", 콜백함수)
     - removeEventListener의 두번째 인자로 전달되는 콜백함수는 addEventListener에서 사용한 함수와 같아야하므로 함수를 전역함수로 정의해놓는 것이 좋다.

<br><br>