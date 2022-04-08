---

layout: post
comments : true
title: 'JSP File Upload'
subtitle: '파일 업로드'
date: 2020-06-02
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 137

---

> 파일 업로드

<br>

- 클라이언트(브라우저)가 전송한 파일을 웹 어플리케이션에서 받아들이는 것
- 서버에서 파일 업로드 라이브러리를 이용하여 업로드된 파일을 처리한다.
  1. commons-fileload 라이브러리
  2. COS 라이브러리
- 업로드 하는 &lt;form> 인코딩형식(encType)을 multipart/form-data로 설정해야 한다.
  - &lt;form> 데이터를 전송하는 기본 형태(인코딩방식)는 "application/x-www-form-urlencoded" 인코딩 방식이다.
  - 위의 방식은 전달 파라미터를 쿼리스트링으로 보낸다.
  - 쿼리스트링으로는 파일의 내용물(컨텐츠)을 전송할 수 없다.
  - 파일의 내용물을 전송할 수 있는 인코딩 방식 "multipart/form-data" 로 &lt;form> 태그에 설정해주어야 한다.
  - multipart 인코딩은 전송할 각 데이터를 boundary(경계선 문자) 를 이용해서 영역을 만들어 그 영역에 데이터를 추가하여 전송한다.
  - 보강 예정!
  <br><br>