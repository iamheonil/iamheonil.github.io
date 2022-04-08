---

layout: post
comments : true
title: 'JSP Context Scope 란?'
subtitle: 'Java Server Pages 컨텍스트 스코프'
date: 2020-05-28
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 132

---

> 컨텍스트영역에 대해서

<br>

- 컨텍스트 영역의 유효범위(Scope)
  - 웹 어플리케이션의 정보(변수)가 영향을 미치는 범위
  - 사용할 수 있는 영역

<br>

- page 영역
  - 논리적으로 가장 좁다
  - 하나의 JSP를 처리하는 동안 유지되는 영역
  - pageContext 내장객체를 이용하여 컨텍스트영역의 정보를 다룬다.
  - 해당 파일 안에서만 사용 가능한 변수를 만들때 Page를 사용하면 된다.
- request 영역
  - HttpServletRequest - URL, Method, Parameter 를 관리하고 사용하는 객체
    - req.getParameter
  - 하나의 요청(Request)을 처리하는 동안 유지되는 영역
    - HTTP Request(요청)이 처리되어 HTTP Response(응답)이 이루어질 때 까지
    - EmpListController 기준이면 Request ' -> EmpListController -> list.jsp -> ' (까지 리퀘스트 영역) Response
    - 컨트롤러에서 모델 값 저장 컨트롤러에서 저장된 데이터를 꺼내서 씀
  - request 내장객체를 이용하여 컨텍스트영역의 정보를 다룬다.
- session 영역
  - 연결된 하나의 클라이언트 (주로 브라우저) 에게 서비스하는동안 유지되는 영역
  - 페이지를 이동해도 유지되는 영역, 같은 클라이언트라면 요청이 새로 발생해도 유지되는 영역
  - 세션을 이용하여 로그인 정보를 기록한다(로그인 유지에 사용된다.)
  - session 객체를 이용한다.
- application 영역
  - 논리적으로 가장 넓다
  - 동일한 어플리케이션이 구동되는 동안 유지되는 영역
  - 톰캣 서버가 켜지고 꺼질 때까지 유지된다.
  - application 객체를 이용한다.

<br><br>