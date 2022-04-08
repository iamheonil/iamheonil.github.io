---

layout: post
comments : true
title: '서블릿의 동작 원리'
subtitle: ''
date: 2020-05-26
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 126

---

> 서블릿의 동작 원리

<br>

- 클라이언트 요청 -> Apache Tomcat 서버(WEB + WAS) -> 서블릿 컨테이너 -> 서블릿 객체 -> service() 호출 -> doGet() 또는 doPost() 호출 -> 서블릿 컨테이너 -> Apache Tomcat 서버 -> 클라이언트 응답

<br>

#### 서블릿 컨테이너, Servlet Container

- 서블릿 처리(동작) 환경을 구축하는 역할
- 서블릿을 생성하고 실행시켜주는 역할을 수행한다.
- WAS서버와 서블릿 객체 사이의 중간다리 역할을 수행한다.

<br>

- HttpServletRequest(HTTP 요청객체), HttpServletResponse(HTTP 응답객체) 두 가지를 생성하여 서블릿에 전달한다.
- 요청 URL-Pattern과 서블릿 객체를 1:1로 따로 매핑해놓고 요청을 기다린다.

<br>

#### 서블릿의 생명주기(Life Cycle)

- 객체 생성 -> init() Method 실행(서블릿 안에 포함되어 있다.) -> service() 실행 -> destroy() 실행
  - 생성자호출 -> 서블릿 초기화 -> doGet(), doPost() 반복적으로 실행 -> 서버 종료
    - doGet(), doPost() 메소드만 실행될 수 있게 잘 작성 해놓으면 일련의 과정은 모두 서블릿 컨테이너가 담당한다, 따라서 개발자는 메소드 작성 이외에 할 게 없다.
- 객체 생성 : 서블릿 객체가 처음으로 사용될 때 수행한다. (URL요청시, 또한 서블릿객체는 Singleton 처리 되어있음)
- init() : 서블릿 객체가 처음 생성된 이후 바로 호출된다. (특별히 하는 일은 없다, 생명주기가 이렇게 설계 되어 있다.)
- service() : 처음 객체 생성될 때를 포함하여 매 URL 요청마다 수행된다.
- destory() : 서버가 종료될 때 호출된다.

<br>

- 서버가 켜진 후 처음으로 서블릿을 사용할 때(첫 요청에 반응할 때)
  - 객체 생성 - init() - service() - Response 순으로 수행한다.
- 객체가 생성된 이후 서블릿을 사용할 때(첫 요청이 아닐 때)
  - 앞에 단계는 생략하고 service() - Response 순으로 수행한다.

<br><br>