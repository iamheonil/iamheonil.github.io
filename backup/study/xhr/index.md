---

layout: post
comments : true
title: 'XHR 객체'
subtitle: ''
date: 2020-06-09
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 145

---

> XHR 객체
>
> XMLHttpRequest

<br>

- AJAX 통신을 하기위한 자바스크립트 기본 내장 객체
- IE 예전 버전에는 존재하지 않는 객체이며 AJAX 기술은 ActiveX 를 이용해 구현된다.
- 크로스브라우징 처리가 필요하다.

<br>

- XHR 객체 속성(property)
  - readyState
    - XHR 객체는 준비 - 전송 - 완료 단계를 거친다. (LifeCycle)
    - readyState 는 각 단계를 표현하는 속성
    - 0 : UNSENT : open() 호출 전 (XHR 객체를 생성한 단계)
    - 1 : OPENED : open() 호출 후
    - 2 : HEADERS_RECEIVED : send() 호출 후 응답을 받기 전까지
    - 3 : LOADING : 다운로드 중(response 메시지를 받는 중)
    - 4 : DONE : XHR 동작 완료(요청, 응답이 완료 된 상태)
  - onreadystatechange
    - readyState 가 변경될 때마다 실행되는 이벤트 리스너, callback 함수로 값을 지정한다.
    - status : HTTP 응답 상태코드
    - statusText : HTTP 응답 상태 메시지
      - 상태 코드(Status) 는 번호 (200, 404, 405, 500 등)
      - 상대 메시지(StatusText) 는 설명 (OK, Not Found, Method Not Allowed 등)
  - responseText
    - 응답 데이터를 String 타입으로 추출(파싱)하는 속성
  - responseXML
    - 응답 데이터를 XML 타입으로 추출(파싱)하는 속성
  - status
  - statusText

<br>

- XHR 객체 메소드 (보강)