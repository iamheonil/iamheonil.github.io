---

layout: post
comments : true
title: 'JSP 입문'
subtitle: 'Java Server Pages'
date: 2020-05-27
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 129

---

> JSP, Java Server Pages

<br>

- 자바코드를 사용하여 서버 페이지를 작성하는 문서(문법)
- HTML 문서 양식에 Java 코드를 삽입하여 프로그래밍할 수 있도록 만들어진 언어
- 서블릿(Servlet)은 Java 코드 양식에 HTML 코드를 삽입하여 작성한다.
- Servlet/JSP 컨테이너(WAS, Tomcat서버)에 의해서 Servlet으로 변환된다.
  - JSP -> Servlet 변환과정을 거친다
  - Jasper 라는 이름을 가진 Component가 수행한다.

<br>

#### JSP 기본 태그

1. 스크립트릿, Scriptlet
   - &lt;% %>
2. 선언, Declaration
   - &lt;%! %>
3. 표현식, Expression
   - &lt;%= %>
4. 지시자, Directive
   - &lt;%@ %>
5. 주석, Comment
   - &lt;%-- --%>

<br>

#### 스크립트릿, Scriptlet

- &lt;% %>
- JSP 파일에서 자바 코드를 작성하기위해 지정하는 영역
- 서블릿으로 변환되면 _jspService() 메소드 내부에 그대로 변환되어 작성된다.
- 자바의 언어 특성상 접근제한자가 존재하는 변수나 메소드 안의 메소드 정의는 불가능하므로 작성시 주의해야한다.
- 수행코드를 작성할 수 있다.(제어문, 메소드호출, 연산 등)

<br>

#### 선언, Declaration

- &lt;%! %>
- JSP 페이지에서 사용할 변수, 메소드를 정의할 때 사용하는 영역
- JSP 를 변환한 서블릿 클래스의 클래스 영역에 정의된다.
- 멤버필드, 멤버메소드가 만들어진다.
- 수행(실행) 코드를 작성하면 안된다(제어문, 메소드호출, 연산 등)

<br>

#### 표현식, Expression

- &lt;%= %>
- HTML 문서에 포함시킬(표현될) 내용을 작성하는 태그
- 스크립트릿을 이용하는 것보다 간단하게 출력할 수 있다.
- 자바 데이터를 HTML 문서에 간편하게 출력할 수 있다.
- Servlet/JSP 컨테이너에 의해 out.print() 코드로 변환된다.
- JSP에 작성된 기분 HTML코드는 out.write() 코드로 변환된다
- 코드의 마지막에 ';'(세미콜론)을 넣으면 안된다.
  - &lt;%= "HIHI" %> -> out.print("HIHI"); 로 변환된다.
  - <% out.print("HIHI"); %> 와 동일한 코드인데 위의 코드가 훨씬 더 간단하다.

<br>

#### 지시자, Directive

- &lt;%@ %>
- Servlet/JSP 컨테이너에게 메세지를 보내기 위한 태그
- JSP가 실행될 때 지시자의 내용을 읽어서 설정값으로 사용할 수 있도록 작성되는 태그
- JSP -> Servlet 으로 변환될 때 필요한 정보를 작성한다.
- 브라우저에게 전달되지 않는다.

<br>

#### 주석, Comment

- 클라이언트 주석
  - HTML 주석
    - &lt;!-- -->
    - 웹브라우저가 태그를 해석하지 못하게 만든다.
  - JS 주석
    - /* */ 또는 //
    - &lt;script> 태그 내에서 사용
    - 브라우저의 자바스크립트엔진이 해석하지 못하게 만든다.
  - CSS 주석
    - /* */
    - &lt;style> 태그 내에서 사용
    - 브라우저의 CSS 엔진이 해석하지 못하게 만든다.

<br>

- 서버 주석
  - JSP 주석
    - &lt;%-- --%>
    - JSP 컨테이너(Jasper)가 해석하지 못하게 만든다
    - 서블릿 코드로 변환되지 않는다.
    - 웹 브라우저로 전송되지 않는다.
  - Java 주석
    - /* */ 또는 //
    - JSP 기본태그들 내에서 사용한다
    - 주로 스크립트릿에서 사용된다.
    - 서블릿 컨테이너(Catalina)가 수행하지 못하게 만든다.
    - 웹 브라우저로 전송되지 않는다.

<br><br>