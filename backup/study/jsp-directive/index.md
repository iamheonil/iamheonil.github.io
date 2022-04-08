---

layout: post
comments : true
title: 'JSP 지시자에 대하여'
subtitle: 'Java Server Pages - Directive'
date: 2020-05-28
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 130

---

> JSP 지시자
>
> &lt;%@ %>

<br>

- 지시자의 종류
  - page 지시자 : JSP 페이지의 전반적인 환경설정
  - include 지시자 : 다른 파일(JSP)의 내용을 JSP페이지 내에 삽입할 때 사용한다.
  - taglib 지시자 : 태그 라이브러리 기능 사용할 수 있도록 설정(활성화)

<br>

#### page 지시자 속성

- Language
  - JSP페이지에서 사용할 서버사이드스크립트의 언어를 지정함
  - 스크립트릿(Scriptlet) 에서 사용하는 언어의 형태를 지정하는 속성
  - 기본값: java
  - 사용가능한 값 : java
- contentType
  - JSP 페이지에서 응답 데이터가 생성되는 형식을 지정하는 속성
  - MIME타입을 사용한다
    - MIME : Multipurpose Internet Mail Extension
    - 전송된 문서(자원)의 형식을 상대방에게 알려주기 위해 사용되는 표현법
    - 원래 이메일에서 사용하던 방식이다
    - 웹 문서(응답 데이터)의 올바른 해석법을 브라우저에게 알리기 위해 Content-Type으로 설정할 때 사용한다.
    - "text/html"; charset=UTF-8" : text 기반의 html문서, 한글인코딩을 UTF-8 인식한다.
    - "text/plain" : 순수한 텍스트, 단순 텍스트
    - "image/jpeg", "image/png ..." : 이미지파일, 이미지압축형식에 따라 JPEG, PNG 등등 설정
    - "application/octet-stream" : 이진 파일 
    - "application/json" : JSON 형식의 데이터
- pageEncoding
  - JSP 파일이 작성된 인코딩 방식
  - JSP 파일 자체의 한글 인코딩 방식을 설정할 때 사용한다.
- import
  - JSP페이지에서 사용할 클래스를 import 하는 속성
  - ex)
    - &lt;@ page import="java.util.Date" %>
    - &lt;@ page import="java.util.List" %>
    - &lt;@ page import="dto.Emp" %>
- extends
  - JSP 페이지의 상위클래스를 지정하는 속성
  - 절대로 건들면 안된다, 서블릿 컨테이너가 알아서 넣어주기 때문
  - &lt;@ page extends="org.apache.jasper.runtime.HttpJspBase" %>
- session
  - JSP 페이지에서 HttpSession 객체를 사용할 지 결정하는 속성
  - true / false 로 값을 지정하는데 기본값은 true이다.
    - HttpSession 클래스 : 자바의 세션 정보 관련 클래스
    - 세션 : 웹 서버가 클라이언트들을 구분하기 위한 식별 방식(기술)
  - 로그인 서비스에 사용된다.
  - 굉장히 중요한 기술이다. 꼭 알아야 한다.
- buffer
  - 서버-클라이언트 간 연결된 출력스트림의 버퍼 크기 설정 속성
  - 기본 크기 8kb
  - none 설정 시 버퍼 사용하지 않음.
  - &lt;@ page buffer="8kb" %>
- autoFlush
  - 버퍼 자동 비우기(flush)
  - 자동으로 응답출력스트림의 flush()를 호출한다.
  - true/false 값으로 설정(기본값은 true)
    - autoFlush를 false로 지정하면 buffer를 none으로 설정할 수 없음
- isThreadSafe
  - JSP 페이지를 Thread-Safe 하게 동작하도록 설정하는 속성
  - true/false 로 설정한다(기본값은 false)
- errorPage
  - JSP에서 에러가 발생하면 이동될 페이지를 지정하는 속성
- isErrorPage
  - 해당 JSP를 에러 처리하는 페이지로 지정하는 속성
  - exception 객체를 다룰 수 있도록 해준다.
  - true/false로 지정한다. (기본값은 false)

<br>

#### incluide 지시자

- 다른 JSP 페이지의 내용이나 HTML 문서를 삽입할 때 사용
- file 속성이 유일하다.
- &lt;%@ include file = "파일경로" %>

<br>

#### taglib 지시자

- 지정된 태그 라이브러리를 활성화 시키는 태그
- 사용자 정의 태그(커스텀태그, Custrom Tag)
  - 표준 태그 이외의 사용자가 만들어낸 비표준 태그
- 태그 라이브러리
  - 사용자 정의 태그를 모아 일종의 규칙(문법)을 부여한 것
- JSTL(JSP Standard Tag Library)
  - 커스텀 태그 중 많이 사용되는 것을 모아서 규약(문법)을 부여한 것
  - JSP 기능을 확장시켜준다.
  - 편의성이 제공된다
  - 반복문, 논리판단(제어문), DB처리, 문자열 처리, XML관련 처리 등을 쉽게 수행할 수 있다.

<br><br>