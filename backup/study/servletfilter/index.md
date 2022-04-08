---

layout: post
comments : true
title: '서블릿 필터'
subtitle: ''
date: 2020-06-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 139

---

> 서블릿 필터, Filter

<br>

- 클라이언트와 서버프로그램 사이에서 요청(request)과 응답(response)을 이용해서 추가작업을 할 수 있도록 만들어진 요소
- 요청 정보의 한글 인코딩을 설정
  - POST 전달 파라미터 설정
- 응답 정보의 한글 인코딩을 설정
  - 응답 메세지의 ContentType을 설정
- 로그인 정보 검사
  - ex) 관리자인지 일반사용자인지 구분
  - ex) 등급별 사용자 구분

<br><br>