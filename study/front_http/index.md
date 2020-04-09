---

layout: post
comments : true
title: 'HTTP 통신(WEB 통신) 과정'
subtitle: ''
date: 2020-04-10
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 79

---

> HTTP 통신(WEB 통신) 과정

<br>

- WEB 서비스
- HTTP 프로토콜 : WEB 서비스에서 사용되는 통신규약
- HTTPS 프로토콜 : 보안 WEB 서비스에서 사용되는 통신규약

<br>

### 웹 서비스는 CS 프로그램

- CS - Server - Client 통신 서비스

<br>

``` html
<!--

		웹 클라이언트											웹 서버
		(브라우저)											(Apache Tomcat)
								Internet / Network
		1. URL 요청			----Request->		 2. 요청 받기
																		3. 요청 처리(요청에 적절한 작업 수행)
		5. 응답 받기		<----Response-		4. 요청에 맞는 응답 생성(주로 HTML)
		6. 응답 데이터 처리(화면에 출력하거나, 다운로드 받거나 등등)

Request 메세지, Response 메세지는 각각 HEADER 영역과 BODY 영역으로 구성되어있다.
HEADER 에는 설정 정보와 같은것들이 들어가 있다.
-->
```

<br>

- HEADER 영역
  - 메세지의 속성, 설정 정보등을 담은 영역
- BODY 영역
  - 메세지의 내용물을 작성하는 영역

<br><br>