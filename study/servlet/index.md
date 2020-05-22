---

layout: post
comments : true
title: '서블릿, Servlet'
subtitle: ''
date: 2020-05-22
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 125

---

> 서블릿, Servlet

<br>

- Servlet = Server + Applet
- 즉, 서버에서 동작하는 애플릿 프로그램이다.
  - [애플릿이란? 위키피디아](https://ko.wikipedia.org/wiki/애플릿)
  - 자바언어로 개발되어 바이트코드 형태로 배포되는 '실행 가능 형태'의 프로그램
  - JVM만 존재한다면 애플릿 프로그램을 실행할 수 있다.
  - 주로 JVM이 포함된 웹서버(톰캣), 애플릿 실행기등에서 동작한다.
  - 플러그인 형태로 JVM을 포함하고 있는 브라우저에서도 동작 가능
  - 실행 가능 형태의 프로그램으로 배포되어 악성코드에 노출 될 이용자들을 위해 실행가능 형태의 프로그램 배포를 중단하고 서버에 올려서 사용하게 되었다, 서버와 Applet 의 합성어가 Servlet 이다.

<br>

- 웹 어플리케이션을 개발하기 위한 자바의 기술(Spec)
  - 서블릿 스펙 (Servlet Spec)
  - 서블릿 스펙에 맞춰 개발된 서블릿 클래스를 '서블릿' 이라고도 말함.
  - MVC 패턴에서 Controller 역할을 담당한다.

<br>

- 서블릿 클래스의 형태

``` java
import javax.servlet.http.HttpServlet;

public class ClassName extends HttpServlet {
  
  // 클라이언트 요청 처리 메소드
  // doGet(), doPost() 오버라이딩
  
}

// 접근 제한자를 반드시 public 으로 해야한다.
// default 포함 이외의 접근 제한자를 사용하면 실행되지 않는다
// 톰캣에 있는 JVM 이 실행시켜주기 때문이다.(톰캣이 자바 클래스의 존재 유무를 모름)

```

<br>

- WEB 서버
  - HTTP 요청과 HTTP 응답을 처리하는 기능을 지닌 서버

<br>

- WAS 서버
  - Web Application Server
  - 웹서버 프로그램을 해석하고 동작시켜주는 기능

<br>

#### 웹서버는 클라이언트의 요청을 받아서 정적인 자원들을 응답한다.

##### HTML, CSS, JS, IMAGE 등의 파일

<br>

#### WAS 서버는 동적인 자원에 대한 요청(서비스)에 대한 처리(해석)를 담당한다.

##### 결과적으로 Servlet 코드를 실행시킨다.

<br>

- 소스코드 위치
  - 서블릿, .java 의 경로
    - 워크스페이스/src/프로젝트명/
  - 컴파일 결과물(바이트코드, .class 파일)의 경로
    - 워크스페이스/build/classes/
  - 톰캣서버 배포(업로드) 경로
    - '실행 가능 형태'의 서블릿(.class)이 업로드 되는 서버의 폴더
    - /.metadata/.plugins/org.eclipse.wst.server.core/tmp0/wtpwebapps/프로젝트명/WEB-INF/classes/
      - tmp0 는 tmp1, tmp2, tmp3 등으로 나타날 수 있다.
      - 현재 사용중이 폴더는 직접 찾아야한다.(대부분 tmp 번호가 높은 번호)


<br><br>