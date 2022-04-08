---

layout: post
comments : true
title: 'Front End Table과 Form 태그'
subtitle: ''
date: 2020-04-11
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 80

---

> 테이블

<br>

- table
  - tr, th, td
  - caption, thead, tbody, tfoot
  - 표를 표현하는 태그

<br>

- table : 표를 만들 때 사용하는 태그, 자식태그들로 행과 열을 표현한다.
- tr : Table Row, 테이블의 각 행을 표현한다.
- th : Table Head, 테이블의 제목을 나타낸다(한 칸, 한 개의 열)
- td : Table Data, 테이블의 데이터를 나타낸다(한 칸, 한 개의 열)

<br>

- caption : 테이블의 이름, 간단한 설명을 작성한다. (테이블 상단 바깥쪽에 위치한다.)
- thead : Table Header, 테이블의 머리글, 코드의 위치에 상관없이 테이블의 최상단 행으로 고정
- tbody : Table Body, 테이블의 본문내용, thead 와 tfoot 의 사이에 들어가게 된다
- tfoot : Table Footer, 테이블의 바닥글, 코드의 위치에 상관없이 테이블의 최하단 행으로 고정

<br>

``` html
<!-- 테이블의 기본 구성 -->

<table>
  
  <tr>
  	<th></th>
    <th></th>
  </tr>
  
  <tr>
  	<td></td>
    <td></td>
  </tr>
</table>

```

<br>

- 테이블 태그 안쪽에는 반드시 td, th를 이용해서 데이터를 표현해야한다.
- td, th 태그는 반드시 tr안에 작성해야한다.

<br>

> form

<br>

- 클라이언트(브라우저)가 서버로 요청을 보낼 때 데이터를 포함시켜주는 태그
- 요청 데이터를 입력할 수 있게 화면을 구성해준다.
  - 요청 파라미터, 전달 파라미터 : 요청 데이터
- action 속성, method 속성을 필수로 작성해야한다.

<br>

``` html
<form action="" method="">
  
</form>
```

<br>

- Action 속성 : 요청 URL을 지정한다.
- Method 속성 : 요청 방식(요청 메소드)을 지정한다.
  - 요청 데이터 전달 방식 : GET, POST
- HTTP 의 요청 방식(리퀘스트 메소드)
  - HTTP Request(HTTP 요청)를 서버로 보낼 때 데이터 전달하는 방식
    - 요청 메세지에는 반드시 요청 방식을 지정해주어야한다.
  - GET method
    - 데이터를 쿼리스트링으로 URL 마지막에 ?를 붙이고 그 뒤에 작성한다.
      - ex) http://domain.com/login/login.html?id=heonil&pw=1234;
      - ex) http://domain.com/search?keyword=JAVA
      - 쿼리스트링 : HTTP 통신에서 전달데이터의 변수명과 값을 표현하는 방식, '변수명 = 데이터' 쌍으로 표현한다.
      - 여러개의 변수는 & (AMPERSAND) 로 구분한다.
  - POST method
    - 전달 데이터를 쿼리스트링으로 요청 메세지의 BODY 영역에 포함시켜 전달하는 방식
  - GET 메소드로 요청을 보내면 전달데이터가 URL에 보이고, POST 메소드로 요청을 보내면 전달데이터가 보이지 않는다.
  - 전달 데이터 없이 URL 요청을 보낼 때 GET 방식을 사용한다.

<br><br>