---

layout: post
comments : true
title: 'FrontEnd jQuery 정규표현식, Regular Expression'
subtitle: '정규 표현식, Regular Expression'
date: 2020-05-13
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
  - \
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
    - {0, 1}로 표현한다
      - ex) {e?le?}
        - "angel" - 매칭 된다. (el)
        - "angle" - 매칭 된다. (le)
        - "also" - 매칭된다. (l)
  - &#43;
    - 1회 이상 연속으로 반복되는 문자(0회는 포함되지 않는다.)
      - {1, } 으로 표현한다.
        - ex) /co+/
          - "count" - "co"에 매칭
          - "cnt" - 매칭 되지 않는다.
  - .
    - 임의의 문자 하나를 표현
      - ex) .n - ?n 패턴을 가지고 있는 문자들을 찾는다.
        - "an apple" - 매칭 된다.(an)
        - "angel" - 매칭 된다.(an)
        - "an apple is on tree" - 매칭 된다.(an, on)
  - {n}
    - n은 정수여야 한다.
    - n번 사용된 경우 매칭
      - ex) /r{3}/
        - "grr" - 매칭 되지 않는다. r 2
        - "grrrrr" - 매칭 된다.
        - "grrr" - 매칭 된다.
  - {n, m}
    - n, m은 정수여야 한다.
      - 최소 n번, 최대 m번 사용될 경우 매칭된다.
      - n <= m, m이 생략된다면 m은 무한으로 허용된다.
        - ex) /a{1,3}/
          - "band" - 매칭 된다.
          - "baaaaaaaam" - 매칭 된다.
          - "bond" - 매칭 되지 않는다.
  - (x)
    - x 를 하나의 그룹으로 매칭
      - ex) /(poo){1,2}/ - poo 를 하나로 인식, 1번 있거나 2번 있는 패턴을 찾는다.
        - "pooh, winnie the pooh" - 매칭 된다. (poo, poo)
        - "poopoopoo" - 매칭 된다. (poopoo, poo)
        - "pooopoopoo" - 매칭 된다. (poo, poo, poo)
  - x|y
    - x 또는 y (or과 똑같다.)
      - ex) apple|banana
        - "5 apple" - 매칭 된다 (apple)
        - "apple and banana" - 매칭 된다 (apple & banana)
        - "red banana" - 매칭 된다 (banana)
  - [xyz]
    - 대괄호 내부에 있는 문자들을 각각 매칭
      - ex) /[abcde]/ == a|b|c|d|e (or와 똑같다)
        - "apple" - 매칭 된다 (a, e)
        - "banana" - 매칭 된다 (b, a, a, a)
    - 만약 [a-e] 라고 사용하면 a부터 e까지의 문자들을 각각 매칭한다.
      - 대표적인 예로는 
      - [a-z] - 소문자 검사
      - [A-Z] - 대문자 검사
      - [0-9] - 숫자 검사
      - [a-zA-Z0-9] - 영문자 숫자
      - [ㄱ-ㅎ] - 자음
      - [ㅏ-ㅣ] - 모음
      - [가-힣] - 한글 전체
      - [ㄱ-ㅎㅏ-ㅓ가-힣] - 한글 모든 조합 문자
  - [^xyz]
    - 제외시킬 문자 집합을 표현한다.
      - ex) /[&#94;abcde/]
        - "apple" - 매칭 된다 (p, p, l)
        - "banana" - 매칭 된다 (n, n)
  - [] 대괄호의 축약형
    - \d - 숫자, [0-9]
    - \D - 숫자가 아닌 것, [&#94;0-9]
    - \w - 단어 문자, 밑줄 포함, 영숫자 문자, [A-Za-z0-9_]
    - \W - 단어가 아닌 것, [&#94;A-Za-z0-9_]
    - \s - space의 약자, 공백문자
    - \S - 공백문자가 아닌 것
    - \t - Tab
    - \n - 개행문자
    - \b - 경계선 문자(boundary)
    - \B - 경계선 문자가 아닌 것
      - ex) /a\b/ - \b 는 경계선 문자이다. "a" 뒤에 경계선인 문자를 매칭한다.
        - "apple banana" - 맨 뒤의 a 한글자 매칭
      - ex) /\ba/ - "a" 앞에 경계선인 문자를 매칭한다.
        - "apple banana" - 맨 앞의 a 한글자 매칭
      - ex) /e\b/ - "e" 뒤에 경계선인 문자를 매칭한다.
        - "apple banana" - "apple" 의 맨 마지막인 e에 매칭된다

<br>

- ? 의 특수 기능
  - 횟수를 표현하는 특수문자( &#42;, &#43;, { } )들은 최대한 많은 데이터를 매칭시키고자 한다.
  - 횟수 표현 문자 뒤에 ?를 사용하게 되면 최대한 짧게 매칭시킨다.
    - ex) /[a-z]/
      - "all test" - 모두 매칭된다. (a l l t e s t)
    - ex)  /[a-z]+/
      - "all test" - 모두 매칭된다. (all, test)
    - ex) /[a-z]+?
      - "all test" - 모두 매칭된다. (a l l t e s t)
    - ex) /[a-z]{2, 3}/ - 최대한에 맞춰 매칭한다.
      - "all test" - 매칭 된다 (all, tes)
    - ex) [a-z]{2,3}? - 조건을 만족하게 되면 바로 Pass
      - "all test" - 매칭 된다 (al, te, st)
  - 정규식 기본 동작은 한번에 최대한 많은 문자를 매칭 시키도록 해야한다.
  - ? 를 이용한 제한 규칙은 최대한 많은 그룹을 매칭해준다.

<br>

- $와 ^을 같이 사용할 때 의미
  - ex) /^eat$/
    - eat이라는 단어만 존재하는 문자열에 매칭된다. 공백, 개행 하나라도 존재하면 No Match
    - &lt;form> 검증(Validation)할 때 사용하는 패턴, 입력된 온전한 단어만 검사할 때 사용한다.

<br><br>