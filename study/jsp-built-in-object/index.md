---

layout: post
comments : true
title: 'JSP 내장 객체'
subtitle: 'Java Server Pages Built in Object'
date: 2020-05-28
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 131

---

> JSP 내장 객체(Built-in Object)

<br>

- JSP 페이지에서 객체 생성없이 바로 사용할 수 있는 객체들
- JSP -> Servlet 변환될 때 자동으로 생성되는 객체들
- Servlet/JSP 컨테이너가 생성해준다.

<br>

- 내장 객체의 종류
  - 입출력(요청, 응답) 관련 객체
    - request : HTTP 요청 정보 객체 (HttpServletRequest)
    - response : HTTP 응답 정보 객체 (HttpServletResponse)
    - out : 응답 객체 출력 스트림 (response.getWriter())
  - 서블릿 관련 객체
    - page : 서블릿으로 변환된 객체
      - JSP 입장에서 보면 나중에 서블릿으로 변환될 자기 자신(this)에 대한 객체
    - config : 서블릿 정보를 저장하고 있는 객체
  - 정보 전달(공유) 객체
    - 중요하다! 잘 이해하고 있어야한다.
      - pageContext : page Scope 영역에 대한 정보 객체
      - request : request Scope 영역에 대한 정보 객체
      - session : session Scope 영역에 대한 정보 객체
      - application : application Scope 영역에 대한 정보 객체
    - 컨텍스트 영역의 스코프(Scope, 유효범위)
      - page, request, session, application
    - 컨텍스트, Context
      - 문맥, 전후사정 이라는 뜻이지만 프로그램에서는 전반적인 설정값, 속성값 등을 표현하는 용어
      - 프로그램과 관련되어 메모리에 로드된 모든 요소
  - 예외 처리 관련 객체
    - exception
      - JSP 페이지에서 예외를 처리할 수 있게 사용되는 객체
      - page 지시자의 isErrorPage 속성을 true설정해야 사용 가능
      - false로 설정하면 서블릿에서도 아예 생성하지 않는다.

<br><br>