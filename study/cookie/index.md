---

layout: post
comments : true
title: '쿠키, Cookie'
subtitle: ''
date: 2020-06-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 141

---
> 쿠키, Cookie

<br>

- 웹 서버가 클라이언트(브라우저)에 정보를 저장하는 기술
- 웹 서버에서 필요할 때 쿠키 정보를 꺼내서 사용할 수 있게 만들어 준다
- 자바에서는 javax.servlet.http.Cookie 객체를 이용하여 관리한다.
- 쿠키 정보는 name = value 쌍으로 이루어진 정보이다.
- 여러개의 쿠키를 저장할 수 있다.
- 브라우저는 도메인별로 쿠키를 저장하고 관리한다.
- 쿠키는 유지시간(MaxAge)을 가지고 있다. - 쿠키 보관 기간
  - 기본값은 무한이며 초단위로 설정 가능하다.

<br>

#### 쿠키의 기본 동작 흐름

1. 클라이언트(브라우저)는 서버에 요청을 보낼 때 항상 쿠키 정보를 포함하여 전달한다.
   - 요청 정보에 포함 시킨다
   - 없으면 보내지 않는다
2. 서버는 클라이언트의 요청데이터에서 쿠키 정보를 확인할 수 있다.
   - 응답 헤더의 Set-Cookie 항목을 통해서 브라우저에 쿠키를 저장할 수 있다.

<br>

#### 서블릿(자바) 코드를 이용한 쿠키 관리

- request.getCookies() : 요청 정보에서 쿠키 정보 꺼내기
- response.setCookie() : 응답정보를 이용해 쿠키 정보 저장시키기

<br>

- JSP 에서도 사용 가능하다.
  - ${cookie } : 쿠키정보 내장객체
  - ${cookie.Key.Value } : Key 에 해당하는 쿠키 값을 출력하는 코드

<br><br>