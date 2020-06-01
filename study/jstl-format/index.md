---

layout: post
comments : true
title: 'JSTL Format Tag'
subtitle: ''
date: 2020-06-01
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 136

---

> JSTL Format 태그

<br>

<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

- formatNumber
  - 문자열을 숫자형식으로 서식화하는 태그
  - &lt;fmt:formatNumber value="값" type="숫자형식" pattern="서식패턴지정" currencyCode="통화코드" currencySymbol="통화심볼" groupingUsed=true | false" var="변수" scope="컨텍스트영역">
    - 위에서 통화는 엔, 원화 등 화폐 가치를 뜻 한다
  - type number(기본값) | currency | percent
    - percent 는 100배 수치변화가 있으니 조심할 것!
    - 0.5 == 50% 로 출력 된다
  - pattern 데이터의 서식, java.text.DecimalFormat
    - &#35; : 유호숫자가 존재하면 숫자를 표시한다
    - 0 : 자리수만큼 0으로 채운다
  - currencyCode : 통화코드, ISO 4217 에서 지정한 표준을 사용한다. (KRW, 대한민국원)
  - currencySymbol : 통화심볼 지정 
  - groupingUsed : 자리수 구분자 삽입 여부 (기본값 true)
- formatDate
  - java.util.Date 데이터를 날짜형식으로 서식화하는 태그 
  - &lt;fmt:formatDate value="값" type="날짜시간형식" dateStyle="날짜표현방식" timeStyle="시간표현방식" pattern="패턴지정 문자" timeZone="시간대" var="변수" scope="컨텍스트영역">
  - type date(기본값) | time | both
  - dateStyle, timeStyle
    - default | short | medium | long | full
  - pattern
    - yy, MM, dd, hh, mm, ss, a, HH, hh, KK, kk, z, Z, X, S
      - 대소문자 구분 해야한다.
      - MM : 월
      - mm : 분
      - HH : 24시간 기준의 시 (자정이 00시)
      - hh : 12시간 기준의 시 (자정이 12시)
      - kk : 24시간 기준 시 (자정이 24시)
      - KK : 12시간 기준 시 (자정이 00시)
      - ss : 초
      - S : 밀리초
      - a : am / pm
      - z, Z, X : time Zone(시간대)

<br><br>