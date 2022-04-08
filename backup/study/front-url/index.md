---

layout: post
comments : true
title: 'URL의 기본구조와 컨텍스트 Path에 대하여'
subtitle: ''
date: 2020-04-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 76

---

> URL 의 기본 구조

<br>

## http://192.168.20.66:9999/Test/hello/hi.html

<br>

- 프로토콜 : http (WEB Service)
- 도메인주소 (IP) : localhost (자기 자신)
- 포트번호 : 9999 (Apache Tomcat 서버에서 정해놓은 포트)
- 컨텍스트 Path(경로) : /Test
- 파일(자원, Resource)의 위치 : /hello/hi.html

<br>
ContextPath 는 아이피주소, 도메인 뒤부터 시작되는, /Test/hello/hi.html 과 같다고 생각한다. <br>
구글링을 해보니까 전부 다 같은 내용을 어디서 복사 붙여넣기만 해놓아서 이해도 안되고 제대로 된 설명도 없다고 생각한다. <br>
자바에서 배운 절대경로와 상대경로와 비슷한거 같기도 한데 정말정말 간단하게 생각해보면 그냥 파일위치..? 인 거 같다 <br>
천천히 생각을 다시 해봐야겠다. <br>

<br>