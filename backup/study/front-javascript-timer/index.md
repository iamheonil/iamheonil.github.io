---

layout: post
comments : true
title: 'FrontEnd JavaScript 타이머함수'
subtitle: 'JavaScript Timer'
date: 2020-05-02
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 102

---

> 타이머 (Timer) 함수

<br>

- setInterval(function, millis) : timerid
  - 지정된 밀리초(millis)마다 function 함수를 반복적으로 실행한다. 타이머 객체의 id를 반환한다.
- setTimeout(function, millis) : timerid
  - 지정된 시간(밀리초) 이후 function 함수를 한 번 실행한다.
  - 타이머 객체의 id를 반복한다.
- clearInteraval(timerid) : undefined
  - 지정된 타이머객체를 즉시 종료시킨다.
  - setInterval, setTimeout 모두 종료 가능

<br><br>