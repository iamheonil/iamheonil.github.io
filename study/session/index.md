---

layout: post
comments : true
title: '세션, Session'
subtitle: ''
date: 2020-06-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 142

---

> 세션, Session

<br>

- 서버가 클라이언트의 요청을 식별하는 방법
- javax.servlet.http.HttpSession 객체를 사용한다
- request(요청객체)를 통해서 HttpSession 객체를 얻어와 사용하게 된다
  - ex) HttpSession session =  request.getSession();
- 서버가 사용자의 정보를 유지하기 위한 기술
  - ex) 로그인 상태
- 쿠키보다 상태 정보에 대한 유지력, 보안성이 좋다
- 쿠키 정보는 클라이언트에 저장되고, 언제든 지워질 위험이 있다
- 세션 정보는 서버가 관리한다
- 클라이언트(브라우저) 별로 따로 관리한다
- 세션 정보는 기본적으로 메모리로 관리한다

<br>

#### 세션의 동작 원리

- 클라이언트의 요청(첫 접속)이 들어오면 서버는 Session ID 를 생성한다.
- 서버가 응답하면서 Set-Cookie 헤더값을 이용해 Session ID 를 클라이언트에게 전송한다.
- 클라이언트는 쿠키로 Session ID를 저장한다
- 클라이언트는 다음 요청때마다 Session ID 쿠키값을 서버로 같이 전송한다
- 서버는 Session ID 별로 세션정보 공간을 관리한다.
- 클라이언트가 종료되면 세션정보가 자등으로 지워진다
- 아파치 톰캣 서버는 기본으로 JSESSIONID라는 이름으로 SESSION ID를 발급한다.

<br><br>