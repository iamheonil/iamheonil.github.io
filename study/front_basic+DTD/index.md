---

layout: post
comments : true
title: 'Front-End 기초와 DTD'
subtitle: 'DTD(Document Type Definition)'
date: 2020-04-09
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 77

---

> Front - End, 화면 구현의 구성 요소

<br>

- HTML - 웹 화면의 구조(골격)를 구성하는 언어
- CSS - 화면의 스타일(모양)을 지정하는 언어
- JavaScript - 화면의 동작을 정의하는 언어

<br>

> HTML

<br>

- Hyper Text Markup Language 의 약자
  - HyperLink - 하이퍼링크가 적용된 문서(다른 문서와 연결된 문서)
  - Markup Language - Tag를 사용하여 문서나 데이터의 구조를 나타내는 언어
- 웹페이지에서 정적인 구조를 표현하는 언어
- 웹페이지의 골격을 개발하는 언어이다.
- 웹 UI 레이아웃(Layout)을 구성한다.
- Tag를 이용하여 개발하는 언어이다.

<br>

Tag란?

``` html
<tag> 와 </tag>로 구성되어 있다.
```
<br>

- [w3schools.com / 참고하기 좋은 사이트](https://www.w3schools.com/)

<br>

```html
<html>, <head>, <body> 위 코드는 반드시 포함 되어 있어야한다.
    
```

<br>

``` html
<!-- 기본 태그들의 형식 -->

<html>
  <head>
    
  </head>
  
  <body>
    
  </body>
</html>

```

<br>

- <HTML> 태그 : HTML문서의 최상위 태그, 모든 태그를 감싸고 있음.
- head 태그 : HTML문서의 정보를 입력하는 태그, 문서 자체의 정보나 설정 값들을 입력한다.
- body 태그 : 화면에 보여질 내용을 작성하는 곳

<br>

> DTD, Document Type Definition

<br>

- DOCTYPE
- 문서 유형 정의
- 브라우저에게 해당 문서가 어떤 유형의 문법을 적용해서 작성되었는지 알리는 문장
- 버전에 맞게 유효성검사(문법 검사)를 할 수 있게 된다.
- 브라우저가 DTD를 확인하고 문서를 확인하는 방법을 결정한다.

<br>

- HTML 5
- XML(eXtensible Markup Language) - 가끔씩 사용할 예정
  - DTD를 적용하면 문법이 적용된다.
- XHTML
  - XHTML 1.0
  - XHTML 1.1 
  - 나는 사용하지 않는다.



<br><br>