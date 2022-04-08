---

layout: post
comments : true
title: '이클립스, TomCat 다운로드, 설치, 연동'
subtitle: '이클립스에서 웹개발을 하기 위한 준비 단계'
date: 2020-04-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 75

---

> 이클립스 최신버전과 아파치 톰캣 다운로드_다운로드부터 이클립스에 적용하기

<br>

[이클립스 패키지 다운로드 페이지](https://www.eclipse.org/downloads/packages/)

Eclipse IDE for Enterprise Java Developers (includes Incubating components) 항목에서 운영체제 확인하여 다운로드 후 압축해제

<br>

[아파치 톰캣 다운로드 페이지](https://tomcat.apache.org/download-90.cgi)

- [Tomcat 9.0.33 zip](http://apache.mirror.cdnetworks.com/tomcat/tomcat-9/v9.0.33/bin/apache-tomcat-9.0.33.zip)

<br>

---

<br>

> 적용하기

<br>

Window 메뉴 - Preferences - 왼쪽의 카테고리에서 Server - Runtime Environments 항목 선택 - Add - 다운받은 해당 톰캣의 버전 선택 - Tomcat Installation Directory 에 Browse 해서 경로 설정 - JRE 자바 JDK 까지 설정 추가 한 후 Apply and Close

<br>

---

<br>

> 이클립스 한글 인코딩 환경 설정

<br>

- UTF-8로 인코딩 설정
- Window 메뉴 - Preferences - encoding 검색 - General - Workspace 클릭 - Text file encoding - MS949 -> Other : UTF-8로 변경 - Apply and Close
- Preferences - Web - CSS Files, HTML Files, JSP Files 3개 항목의 인코딩 형식을 UTF-8(ISO 10646)로 설정

<br>

---

<br>

> 서버 추가하기

<br>

Servers 탭 - No Servers are available ~~~ 클릭 - 내가 추가 한 버전을 클릭하고 Runtime environment 버전 맞는지 확인 후 Finish

<br>

Ports 의 HTTP/1.1 의 포트를 수정해주자. 나 같은 경우는 9999를 사용한다. 모든 개발환경은 9999 를 사용 할 예정.

<br>

---
<br>
> 프로젝트 생성하고 서버에 적용하기

<br>

- File - New - Dynamic Web Project
- 서버 우클릭 - Add and Remove - 만든 프로젝트 오른쪽으로 이동 - Finish


<br><br>