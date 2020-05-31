---

layout: post
comments : true
title: 'JSTL, JSP Standard Tag Library'
subtitle: ''
date: 2020-05-30
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 135

---

> JSTL, JSP Standard Tag Library

<br>

- JSP 에서 사용 가능한 표준 태그 라이브러리
- JSP 코드의 가독성이 좋아진다.
- 자바코드를 작성할 상황을 최소화 시켜준다.
- 추가 라이브러리 파일이 필요하다
- JSP 페이지에서 taglib 지시자를 이용하여 활성화해주어야 한다

<br>

### JSTL 이 제공하는 5가지 커스텀 태그

- core
  - 논리 판단(조건문), 반복문 등의 제어문을 지원하는 태그
  - 다른 JSP 호출하는 기능의 태그도 포함
- format
  - 날짜, 숫자, 시간 데이터의 서식을 지정하는 태그
- sql
  - 데이터베이스 처리
- xml
  - XML 문서에 대한 처리
- functions
  - 문자열 처리 함수를 사용할 수 있게 해주는 기능
  - 단독 태그로 사용하지 않고 EL 과 함께 사용한다.

<br>

#### JSTL taglib 지시자

- JSTL 태그 라이브러리를 활성화하는 지시자가 필요하다.
- <&lt;taglib prefix="접두어" uri="라이브러리 식별값" %>

<br>

#### Core 일 경우,

&lt;%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>

<br>

#### Format 일 경우,

&lt;%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<br>

#### Sql 일 경우,

&lt;%@ taglib prefix="sql" uri="http://java.sun.com/jsp/jstl/sql" %>

<br>

#### Xml 일 경우,

&lt;%@ taglib prefix="x" uri="http://java.sun.com/jsp/jstl/xml" %>

<br>

#### Functions 일 경우,

&lt;%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>

<br>

<br>

### JSTL Core 태그 라이브러리

- out => JSP Writer 를 이용한 브라우저 출력

  - &lt;c:out value="출력값" defalue="value 값이 null 일 때 출력될 값" escapeXml="true | false" />
  - escapeXml 속성
    - true - &lt;, &gt;, &, ", ' 를 문자 그대로 출력한다(기본값)
    - false - 태그를 반영하여 출력한다.

- set => JSP변수 설정, 등록(컨텍스트 영역)

  - &lt;c:set var="변수명" value="값" [scope="영역"] />
  - &lt;c:set var="변수명" [scope="영역"]> 값 &lt;/c:set>
    - scope : page(기본값) | request | session | application
  - var="변수명" 속성 대신 target 을 사용해서 객체의 내부 프로퍼티의 값을 설정할 수 있다. (객체, Map)
  - &lt;c:set target="&lt;%=객체변수명 %>" property="키" value="값" />
  - &lt;c:set target="${객체변수명 }" property="키" value="값" />

- remove => 변수 제거

  - &lt;c:remove var="변수명" [scope="영역"] />
    - scope를 지정하지 않으면 모든 컨텍스트 영역의 변수를 제거한다.

- if => 조건문

  - &lt;c:if test="조건식"> 조건식 결과가 true일 때 수행하는 코드 &lt;/c:if>
  - &lt;c:if test="조건식" var="결과저장할변수" scope="컨텍스트영역지정"> &lt;/c:if>
    - var로 지정된 변수에 true 또는 false 가 저장된다
    - 다른 컨텍스트 영역과 수행결과를 공유할 때 사용한다
    - 조건식 결과가 true일 때 수행하는 코드

- choose => 다중 조건문

  - &lt;c:choose> 
    &lt;%-- 조건1이 true일 때 수행하는 영역 --%>
    &lt;c:when test="조건1">
    &lt;/c:when> 

    &lt;%-- 조건1이 true일 때 수행하는 영역 --%>
    &lt;c:when test="조건2">
    &lt;/c:when>
    &lt;c:otherwise>
    &lt;%-- 모든 조건이 false일 때 수행 --%>
    생략 가능하다.
    &lt;/c:choose>

- forEach => 반복문, 컬렉션이나 맵의 Iterator

  - <c:forEach var="변수" begin="시작값" end="끝값" step="증가값" items="반복될객체" varStatus="반복정보객체">
    // ${var } 변수를 이용한 코드
    &lt;/c:forEach>

- forTokens => 문자열을 split한 결과배열의 토큰값으로 반복

  - &lt;c:forTokens var="변수" items="원본문자열" delims="구분자">
    ${변수 }
    &lt;/c:forTokens>
    - items 의 문자열을 delims로 split하여 결과를 순서대로 var에 지정한 변수에 담아 반복하는 태그

<br><br>