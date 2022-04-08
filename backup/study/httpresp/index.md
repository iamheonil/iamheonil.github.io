---

layout: post
comments : true
title: 'HTTP 요청과 doGet, doPost 메소드'
subtitle: ''
date: 2020-05-26
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 127

---

> HTTP 요청, GET, POST 메소드

<br>

- GET 메소드는 서버의 자원(데이터)을 조회할 때 사용한다.
- POST 메소드는 서버의 자원(데이트)을 삽입, 수정, 삭제할 때 사용한다.
  - SELECT 문과 비슷한 기능은 GET 메소드
  - INSERT, UPDATE, DELETE 는 POST 메소드
- 전달 파라미터가 단순하거나 없으면 GET을 사용한다.
- 전달 파라미터가 크거나 길거나 민감한 정보일 경우 POST를 사용한다.

<br>

- GET은 URL 뒤에 쿼리스트링으로 작성되어 전달 파라미터가 서버로 전달된다.
  - HTML Form 태그 실습해본 거 처럼 URL에 데이터가 노출되기 때문에 위험하다.
- POST는 요청메세지의 BODY 영역에 쿼리스트링으로 작성되어 전달 파라미터가 서버로 전달된다.
  - 데이터를 1차적으로 숨길 수 있다.

<br>

#### GET method 로 요청이 발생하는 상황

- 단순히 URL 만 요청했을 때 (브라우저에서 주소입력창에 URL 을 입력했을 때)
- 정적인 파일을 요청할 때 (파일, HTML, CSS, JS, IMAGE 등)
- 폼태그에서 method를 get으로 설정하고 submit 했을 때
- &lt;a> 링크를 클릭했을 때
- location.href = "URL" 을 이용한 페이지 이동

<br>

#### POST method 로 요청이 발생하는 상황

- form 태그에서 method 를 post 로 설정하고 submit 했을 때, 단 한가지 상황

<br><br>