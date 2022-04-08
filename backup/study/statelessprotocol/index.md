---

layout: post
comments : true
title: '무상태 프로토콜, Stateless Protocol'
subtitle: ''
date: 2020-06-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 140

---

> 무상태 프로토콜, Stateless Protocol
>
> 쿠키(Cookie)와 세션(Session)에 대하여

<br>

- 통신 상태 정보를 저장하지 않는 프로토콜
- 통신 정보 : 서버 - 클라이언트 간의 통신 정보
- 새로운 요청이 발생하면 서버는 이전에 왔던 요청의 같은 클라이언트인지 구분하지 않는다.
- 웹(HTTP)에서는 요청마다 독립적인 통신으로 판단한다.
- 프로토콜만으로는 동일한 사용자의 연속된 요청인지 판단할 수 없다.
- 그러므로 상태관리 메커니즘(기술)이 필요하다.

<br>

#### 상태관리 메커니즘

- 사용자(Client)의 정보를 관리(유지)하는 기술
  - 쿠키, Cookie
    - 서버의 정보를 클라이언트(브라우저)에 저장하는 기술
  - 세션, Session
    - 서버 - 클라이언트 간의 정보를 교환하는 기술
    - 서버 - 클라이언트 연결 상태를 유지하는 기술

<br><br>