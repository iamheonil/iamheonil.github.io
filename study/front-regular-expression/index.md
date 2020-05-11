---

layout: post
comments : true
title: 'FrontEnd 정규표현식'
subtitle: '정규 표현식, Regular Expression'
date: 2020-05-12
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 116

---

> 정규 표현식, Regular Expression

<br>

## [정규 표현식 테스트 사이트](https://regexr.com/)

<br>

- 특정 규칙을 가진 문자열이나 문자열 집합을 표현하는 데 사용하는 형식 언어(Formal Language)
- 문자열에서 특정 패턴의 문자열을 검색하거나 치환할 때 사용한다
- 형식에 맞는 데이터를 입력했는지 검증할 때 사용한다(&lt;form>검증, Validation)
- 정규식 이라고도 불린다.

<br>

- 정규 표현식 생성 방법
  1. 정규식 리터럴 상수 정규식을 '/'(슬래쉬)로 감싸는 방법으로 표현한다.
     - ex) var regEx = /abc/
  2. RegExp 객체를 생성
     - RegExp 객체의 생성자 함수를 호출하는 방법으로 표현한다.
     - ex) var regObj = new RegExp("abc")

<br>

- 정규 표현식 사용 패턴
  - 단순 패턴
    - 완전히 일치하는 문자열을 대응시킬 때 사용
    - ex) /abc/ -> "abc"
    - ex) /Hello/ -> "Hello RegExp"
  - 특수 문자 패턴
    - 특수한 형식의 패턴을 적용하여 문자열을 대응시킬 때 사용

<br>

- 정규식 특수문자
  - \, ₩
    - 다음 문자로 오는 값이 특수 문자가 아니라 평범한 문자임을 알림
      - ex) /a&#42;/ =-> /a\ &#42;/
    - 뒤에 오는 문자와 합쳐서 특수 문자가 되기도 한다.
      - ex) /\d/ -> 숫자(Digit)
  - ^
    - 데이터의 시작에 매칭
      - ex) /^A/ -> 여기^ㅓ부터 데이터가 시작됩니다. 라는 뜻, 문자열의 시작이 'A'인 패턴
      - "an A" - 매칭되지 않는다
      - "A b" - 매칭 된다.
      - "An" - 매칭 된다.
  - $
    - 데이터의 끝에 매칭
      - ex) /t$/
      - "eater" - 매칭되지 않는다.
      - "eat" - 매칭 된다.
  - &#42;
    - 0회 이상 연속으로 반복되는 문자
    - {min, max}
    - {0, } 으로 표현하기도 한다.
      - {0, } 으로 표현하게 된다면 0회 이상 반복되면 찾는다.
      - /gr*/ == /gr{0, }/
        - "grrrrrrrrrrr" - 매칭된다
        - "grow" - 매칭된다
        - "get" - 매칭된다
        - "program" - 매칭된다
        - "js Programming" - 매칭된다
  - ?
    - 0회 또는 1회로 사용되는 문자
    - {0, 1}로 표현된다
      - ex) {e?le?}
        - "angel" - 매칭 된다. (el)
        - "angle" - 매칭 된다. (le)
        - "also" - 매칭된다. (l)
- $와 ^을 같이 사용할 때 의미
  - ex) /^eat$/
    - eat이라는 단어만 존재하는 문자열에 매칭된다. 공백, 개행 하나라도 존재하면 No Match
    - &lt;form> 검증(Validation)할 때 사용하는 패턴, 입력된 온전한 단어만 검사할 때 사용한다.

<br><br>