---

layout: post
comments : true
title: 'FrontEnd JavaScript Closure'
subtitle: 'JavaScript 클로저'
date: 2020-05-03
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 103

---

> 클로저, Closure

<br>

- Free Variable(자유변수) 와 함께 손꼽히는 중요한 개념이니 꼭! 기억 해야 한다.
- 함수 스코프의 외부로 반환된 내부함수가 자신이 선언(정의)되었을 때의 스코프(환경, 상태)를 기억하는 것 - Lexical Scope
- 함수 스코프가 종료되었더라도 클로저함수를 호출하면 클로저 함수가 선언되었을 때 만들어진 스코프에 접근할 수 있다.
- 클로저 함수에 의해 접근할 수 있는 변수를 자유변수(Free Variable)이라고 한다.
- 자유변수는 새롭게 만들어진 것이 아니라 최초의 변수공간을 계속 사용하는 것이므로 값의 변화가 적용되고, 최신값으로 유지된다.

<br><br>