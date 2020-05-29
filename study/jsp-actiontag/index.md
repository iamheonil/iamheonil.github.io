---

layout: post
comments : true
title: 'JSP Action Tag 란?'
subtitle: 'Java Server Pages Action Tag'
date: 2020-05-29
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 133

---

> JSP 액션 태그, Action Tag

<br>

- JSP 의 문법 요소 중 하나
- JSP 페이지에서 특정 동작을 수행하도록 만든 태그
- 페이지와 페이지 사이의 제어, 이동 등의 기능을 제공한다.

<br>

#### 형식

&lt;jsp:수행명령 속성="속성값">&lt;/jsp:수행명령>

- 기본적으로 태그로 이루어져 있기때문에 여는태그, 닫는태그 모두 사용해야한다.

<br>

- &lt;jsp:useBean id="bean 변수명" class="클래스명(DTO 명)" [scope="스코프지정"] >
  - 자바빈(JavaBean) 생성
  - JSP 페이지에서 사용할 JavaBean 객체를 생성하고 지정한 scope 영역의 컨텍스트 정보로 저장한다.
  - scope 영역을 지정하지 않으면 page 영역에 저장된다.
  - scope : page(기본값) | request | session | application

<br>

- &lt;jsp:setProperty name="bean이름" property="필드명" [value="값설정"] />
  - JavaBean 프로퍼티에 값을 설정한다.
  - DTO 클래스의 setter 를 실행한다.

<br>

- &lt;jsp:getProperty name="bean이름" property="필드명" />
  - JavaBean 프로퍼티 값을 가져온다
  - DTO 클래스의 getter 를 실행한다.

<br>

- 페이지 이동 (Servlet)

  - 서버에서 수행하는 화면 전환
  - 클라이언트 입장에서 보고있는 화면이 변경된다.

- 포워드(forward) 방식

  - 요청 URL을 유지한다

  - 보여지는 문서(주로 HTML) 의 내용만 바꿔치기한다. (대부분 JSP 이용)

  - request(요청객체) 가 유지된다.

  - response(응답객체) 가 유지된다.

    --------------------------------------------------

    - Request Scope 의 컨텍스트 영역이 유지된다. - 이게 중요하다.
    - 모델값을 request 영역에 저장해서 Controller -> View 전달할 수 있게 한다.

    ------------------------------------------------

    - ex) request.getRequestDispatcher("페이지URL").forward(request, response);

- 리다이렉트(redirection) 방식

  - 요청 URL을 변경한다

  - 새로운 요청이 발생하면서 화면 전환이 된다.

  - 새로운 Request 객체가 생성된다. (포워드 방식과 다른점)

  - request 컨텍스트 영역도 새롭게 생성된다.

  - request 객체, response 객체 둘 다 유지되지 않는다.

  - ex)
    BoardInsertController 게시글 작성 - /board/insert [GET]
    /board/insert.jsp 게시글 작성 폼 (JSP)

    BoardInsertController 작성 정보 DB저장 - /board/insert [POST]

  - ex)
    response.sendRedirect("페이지URL");

<br>

- &lt;jsp:forward page="이동할페이지"> &lt;/jsp:forward>
  - JSP에서 포워딩을 수행하는 태그
  - 전달 파라미터를 전달하고 싶다면 &lt;jsp:param value="값" name="변수명" /> 을 자식태그로 사용한다.
    - ex) &lt;jsp:forward page="userInfo.jsp">
      &lt;jsp:param value="alice" name="id" />
        	&lt;/jsp:forward>
    - request.getParameter() 메소드를 이용해서 데이터를 사용할 수 있다.

<br>

- &lt;jsp:include page="삽입할페이지"> &lt;jsp:include>
  - &lt;jsp:include page="삽입할페이지"> &lt;jsp:param name="이름" value="값" /> &lt;/jsp:include>
  - JSP 페이지에 다른 페이지를 추가할 때 사용
    - include 지시자와 include 액션은 둘 다 JSP 페이지에 다른 페이지를 추가할 때 사용한다.
    - include 지시자와 include 액션의 차이점
      - include 지시자는 JSP 코드를 하나로 합치고 나서 컴파일한다.
      - include 액션은 각각의 JSP 를 컴파일하고 결과물을 합친다.
      - include 지시자는 파라미터를 전달할 수 없다.
      - include 액션은 파라미터를 전달할 수 있다.

<br>

### 자바 빈, Java Bean

- JSP 에서 사용하는 자바 클래스의 객체
- JSP 에서 사용할 정보를 저장하는 저장소로 사용한다.
- 자바 빈 설계원칙(규약)에 맞게 작성한 클래스를 사용한다.
- DTO가 자바빈을 만드는 클래스로 사용된다.
- 인스턴스화 된 대상을 지칭하는 용어이다.

<br>

- 자바 빈 설계 원칙 - DTO 작성 방법
  - 별도의 로직을 구현하지 않는다.
  - 기능을 가지고 있는 메소드를 구현하지 않는다.
  - 패키지가 반드시 있어야한다.
    (패키지가 없으면 디폴트 패키지라고 하는데 디폴트 패키지도 사용하면 안된다.)
  - public 클래스로 생성한다.
  - 멤버필드는 private 로 지정한다.
  - 생성자는 디폴트 생성자가 반드시 존재해야한다.
  - 매개변수가 있는 생성자는 작성하지 않는것이 좋다.
  - 생성자를 아예 작성하지 않는 것이 좋다.
  - 캡슐화가 되어있어야 한다.
  - 멤버필드에 대한 setter, getter 를 구현한다.
  - setter, getter 접근제한자는 public 으로 한다.
  - getter 의 반환타입이 boolean 이면 메소드명을 get 대신 is 로 시작할 수 있다.
  - JSP 페이지에서 등록된 자바빈의 멤버 필드를 Property(프로퍼티) 라고 한다.

<br>

#### POJO, Plain Old Java Object

- 객체의 규모를 줄이고, 불 필요한것을 최소화하여 가볍게 만든 객체
- extends 나 implemnet 를 최소화하여 작성한다.
- 최대한 Object만 부모로 가지도록 설계
- 애플리케이션의 규모가 커지면서 개발해야하는 기능이 하나의 클래스에 몰려서 캡슐화된 클래스의 규모가 커지게되자 나온 개념
- 목적
  - 가볍고, 유연하고, 간단하게  작성된 객체를 만들자

<br><br>