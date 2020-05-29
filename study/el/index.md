---

layout: post
comments : true
title: 'EL, Expression Language'
subtitle: ''
date: 2020-05-29
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 134

---

> EL, Expression Language

<br>

basic Tag - action Tag - EL

<br>

- JSP 에서 값을 출력하는 코드를 쉽게 사용할 수 있도록 만들어진 문법
- 표현식(Expression Tag, &lt;%= %>) 과 비슷한 역할을 수행한다.
- 주로 컨텍스트 정보를 다루거나 출력할 때 사용한다.
- JSTL 과 함께 사용하기에 적합하다.

<br>

#### EL 구문 형식

- ${ } ( $( ) - jQuery 와 헷갈리면 안된다. )
  - ex) ${10+20} => 30이 브라우저 화면에 출력된다.

<br>

- EL 연산자
  - 산술
    - +, -, *, /, div, %, mod
  - 관계
    - ==, eq, !=, ne, <, lt, >, gt, <=, le, >=, ge
  - 조건
    - (조건식)? data1: data2
  - 논리
    - &&, and, ||, or, !, not
  - null검사 연산자
    - ex) ${empty obj} => obj 객체가 null 이라면 true 반환

<br>

#### EL 내장 객체

- pageContext
  - JSP의 pageContext 내장 객체와 동일
- pageScope
  - JSP의 page scope 의 컨텍스트 정보
  - ex) ${pageScope.data } => &lt;%=pageContext.getAttribute("data") %>
- requestScope
  - JSP의 request scope의 컨텍스트 정보
- sessionScope
  - JSP의 session scope의 컨텍스트 정보
- applicationScope
  - JSP의 application scope의 컨텍스트 정보
- param
  - 전달파라미터에 접근할 수 있도록 한다
  - ex) ${param.data } => &lt;%=request.getParameter("data") %>
- paramValues
  - request.getParameterValues("이름") 의 기능을 수행한다.
    - 같은 name으로 여러 개의 데이터(값)을 전달했을 때 사용한다.
      - ex) checkbox
      - ex) ${paramValues.hobby[0] }
        ${paramValues.hobby[1] }
- header
  - 요청 header 정보를 사용할 수 있다.
    - ex) ${header.host } => &lt;%=request.getHeader("host") %>
- headerValues
  - request.getHeaderValues("이름")을 사용하는 것과 같다.
- cookie
  - request.getCookie() 로 구한 Cookie[] 을 Map으로 사용할 수 있도록 해준다.
- initParam
  - application.getInitParam("이름")의 정보를 사용할 수 있다.
    - 초기화 파라미터(Inital Parameter)
      - 웹 어플리케이션에 설정된 기본 파라미터(속성값)
      - application 객체에 저장시켜둔 공용 데이터
      - 모든 클라이언트가 확인할 수 있도록 미리 저장해둔 상태값