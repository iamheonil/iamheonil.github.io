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

> JavaScript 변수 선언 키워드

<br>

- var
  - 같은 이름의 변수를 여러번 선언해도 오류가 발생하지 않는다.
  - ex) var data1 = 10; // var data1 = 20; --> data변수가 10으로 초기화 되었다가 20이 대입된다.
- let
  - 같은 이름의 변수를 여러 번 선언할 수 없다.
  - ex) let data2 = 10; // let data2 = 20; --> 에러발생, data2가 이미 선언됐음.
- const
  - let과 같음
  - 변수값 초기화는 가능하지만 이후에 대입이 안된다.
  - 변수값 초기화는 필수(하지 않으면 에러가 발생한다.)

<br>

- 적용되는 스코프
  - var : function scope
  - let, const : block scope
  - var 변수는 함수 내 지역스코프 특성이 부여된다.
  - let, const는 블록에서 만들어진 변수라면 지역스코프 특성이 부여된다. (익명블록, 제어문 등등)

<br>

- Hoisting (호이스팅, 끌어올리기)
  - 변수의 선언코드나 함수의 정의코드가 해당 스코프의 가장 처음 부분에 작성된 것처럼 동작하게 만드는 특성
  - 실제는 코드영역 첫부분에 작성되어 있지 않지만 미리 선언이 완료된 것처럼 동작되는 것을 말한다.
  - var, let, const 모두 호이스팅이 발생한다.
  - var는 실제 선언코드 이전에 접근 가능하다
  - let,const 는 실제 선언코드 이전에 접근하는 것을 금지시킨다.

<br>

``` javascript
console.log(data3);	// 에러나지 않고 undefined 출력(호이스팅)

var data3 = 100;

console.log(data3); // 정상적으로 100 출력
```

<br><br>