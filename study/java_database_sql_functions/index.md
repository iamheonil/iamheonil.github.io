---

layout: post
comments : true
title: 'Database Functions'
subtitle: '오라클 내장 함수에 대하여'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 44

---

 
> 오라클 내장 함수, SQL Functions

<br>

- 오라클 DB에 포함된 Built-in 함수들
- 오라클 SQL API Functions
- 단일 행 함수, Single Row Functions
  - 조회되는 행 하나 하나의 요소에 함수, 수행결과가 적용 된다.
- 그룹 함수, Group Functions (복수 행 함수)
  - 행들의 조회 결과를 그룹지어진 여러개의 요소에 함수, 결과가 적용 된다.

<br>

> 문자 함수, Character Function

<br>

- length - 문자에 사용한다, 문자열의 길이를 알려주는 함수
- lengthB - 문자열의 길이를 반환하는데, Byte 크기로 반환한다.
- COUNT(*) - 그룹함수이며, 행의 갯수를 알려준다.
- DUAL 테이블 - DBA가 소유하고 있으며 연산에 사용한다. 기본으로 들어가 있다. 
  - 오라클에서 제공해주는 테스트용 테이블 (Dummy 테이블)
  - 연산의 결과나 함수의 결과, 가상컬럼 등을 확인할 때 사용한다.
  - ,(COMMA) 로 구분하여 여러개의 연산을 수행할 수 있다.
- Upper - 해당 문자열 모두 대문자로 변환한다.
- Lower - 해당 문자열 모두 소문자로 변환한다.
- INITCAP - 문자열 맨 첫번째 문자를 대문자로 나머지는 모두 소문자로 변환한다.
- INSTR - 해당 문자열에서 해당 문자의 위치를 숫자로 나타낸다.
- SUBSTR - 해당 문자열에서 n번째 인덱스 이후를 문자열로 잘라서 출력한다.
  - SUBSTR('String', 2, 2) - 이런 식으로 n번째 인덱스에서 n글자만큼 자르는 것도 가능하다.
- Padding - 문자를 표현하기 위해 공간을 확보하고 문자를 채워넣는다.
  - LEFT PADDING - lpad()
    - ex) SELECT lpad('SQL', 10) FROM DUAL;
    - 오른쪽 정렬을 한 것 같은 느낌을 줄 수 있다.
  - RIGHT PADDING - rpad()
- TRIM - 데이터의 양 끝단에 있는 공백을 제거한다.
- 



###### 추후 수강한다면 별도의 포스트로 추가 예정

<br>

``` sql
-- 문자 함수 문제

-- 'hELlo' 모두 대문자로 변환 -> HELLO
SELECT Upper('hELlo') FROM DUAL;

-- 'hELlo' 모두 소문자로 변환 -> hello
SELECT Lower('hELlo') FROM DUAL;

-- 'hELlo' 이니셜(첫글자) 대문자 -> Hello
SELECT INITCAP('hELlo') FROM DUAL;

-- 'Alice Bob'의 문자열 길이 -> 9
SELECT LENGTH('Alice Bob') FROM DUAL;

-- '안녕하세요'의 문자열 길이 -> 5
SELECT LENGTH('안녕하세요') FROM DUAL;

-- 'Alice Bob' 문자열 바이트 수 -> 9
SELECT LENGTHB('Alice Bob') FROM DUAL;

-- 'ACE 안녕하세요'문자열 바이트 수 -> 19
SELECT LENGTHB('ACE 안녕하세요') FROM DUAL;

-- (오라클은 한글 인코딩을 UTF-8을 기본으로 하며
--  UTF-8은 한글 한글자에 3바이트가 필요하다)

-- 'ABCDEFGHI'에서 'D' 의 위치 -> 4
SELECT INSTR('ABCDEFGHI', 'D') FROM DUAL;

-- 'ABCDEFGHI'에서 'DEF'문자열의 위치 ->4
SELECT INSTR('ABCDEFGHI', 'DEF') FROM DUAL;

-- 'ABCDEFGHI'에서 'DF'문자열의 위치 -> 0
SELECT INSTR('ABCDEFGHI', 'DF') FROM DUAL;

-- '안녕하세요'에서 '하'문자열의 위치 -> 3
SELECT INSTR('안녕하세요', '하') FROM DUAL;

-- 'ABCABCDDD'에서 'C'문자열의 위치 -> 3
SELECT INSTR('ABCABCDDD', 'C') FROM DUAL;

--'Oracle SQL Developer'에서 5번째 인덱스 이후의 문자열로 자르기
SELECT SUBSTR ('Oracle SQL Developer', 5) FROM DUAL;

--'Oracle SQL Developer'에서 5번째 인덱스부터 5글자로 자르기
SELECT SUBSTR ('Oracle SQL Developer', 5, 5) FROM DUAL;

--'오라클 SQL'에서 2번째 인덱스부터 5글자로 자르기
SELECT SUBSTR ('오라클 SQL', 2, 5) FROM DUAL;

--'안녕하세요오라클'에서 3번째 부터 자르기
SELECT SUBSTR ('안녕하세요오라클', 3) FROM DUAL;
```

<br>



``` sql
SELECT LENGTH('Apple 안녕') LENGTH, 
length2('Apple 안녕') LENGTH2, length4('Apple 안녕') LENGTH4, 
lengthb('Apple 안녕') LENGTHB, lengthc('Apple 안녕') LENGTHC FROM dual;
-- 실행결과
-- LENGTH LENGTH2 LENGTH4 LENGTHB LENGTHC
--   8	    8	    8	    21		 8

-- 캐릭터셋(인코딩) 확인
SELECT * FROM nls_database_parameters
WHERE PARAMETER = 'NLS_CHARACTERSET'; 

```



<br>

> 숫자 함수, Numeric Function

<br>

- ABS - 해당 수의 절대 값을 출력한다.
- ROUND - 해당하는 자리를 지정하여 반올림한다.
- TRUNC - 해당하는 자리 이하 모두 버린다.
- MOD - n1과 n2 를 나눈 나머지를 출력한다.
- CEIL - 해당 소수점을 올린다.
- FLOOR - 해당 소수점을 내린다.
- POWER - n1의 n2 제곱을 구한다.
- SQRT - n1의 제곱근을 구한다.

###### 추후 수강한다면 별도의 포스트로 추가 예정

<br>

<br>
<br>

``` SQL
-- SQL 숫자 함수 퀴즈

-- 12.523 -> 소수점이하 반올림
SELECT round(12.523) FROM DUAL;

-- -12.723 -> 소수점이하 반올림
SELECT round(12.723) FROM DUAL;

-- 12.567 -> 소수점 3째자리에서 반올림
SELECT round(12.567, 2) FROM DUAL;

-- 12345 -> 1의 자리에서 반올림
SELECT round(12345, -1) FROM DUAL;

-- 56789 -> 10의 자리에서 반올림
SELECT round(abs(56789), -2) FROM DUAL;

-- 12.456 -> 소수점이하 버림
SELECT TRUNC(12.456, 0) FROM DUAL;

-- 12.456 -> 소수점 3째자리에서 버림
SELECT TRUNC(12.456, 2) FROM DUAL;

-- 12345 -> 1의자리에서 버림
SELECT TRUNC(12345, -1) FROM DUAL;

-- 56789 -> 10의자리에서 버림
SELECT TRUNC(56789, -2) FROM DUAL;

-- 13을 8로 나눈 나머지
SELECT MOD (13, 8) FROM DUAL;

-- 12.345 올림 -> 13
SELECT CEIL(12.345) FROM DUAL;

-- -12.567 올림 -> -12
SELECT CEIL(-12.567) FROM DUAL;

-- 12.567 내림 -> 12
SELECT FLOOR(12.567) FROM DUAL;

-- 12.123 내림 -> 12
SELECT FLOOR(12.123) FROM DUAL;

-- -12.567 내림 -> -13
SELECT FLOOR(-12.567) FROM DUAL;

-- -12.123 내림 -> -13
SELECT FLOOR(-12.123) FROM DUAL;

-- 3의 4제곱 -> 81
SELECT POWER(3, 4) FROM DUAL;

-- 3의 -1 제곱 -> 0.33333333333
SELECT POWER(3, -1) FROM DUAL;

-- 9의 제곱근 -> 3
SELECT SQRT(9) FROM DUAL;

-- 11의 제곱근 -> 3.3166...
SELECT SQRT(11) FROM DUAL;
```

<br>

> 날짜 함수, Datetime Function

<br>

- DATETIME - 날짜시간 타입 -> 문자 타입(서식을 지정)
  - SELECT to_char(sysdate, 'yyyy/mm/dd hh24:mi:ss') NOW FROM dual;
- MONTHS_BETWEEN - 개월수의 차이를 계산한다.
- next_day(sysdate, 'd') - 오늘로부터 가까운 d요일이 언제인지 yy/mm/dd 형식으로 출력한다.
- trunc(date) - 시간을 자정(00시 00분 00초)으로 맞춘다. 
  - trunc(sysdate) 와 sysdate 는 보이는 날짜는 같지만 시간은 서로 다른 값을 가진다.

<br>

> 변환 함수, Conversion Function

<br>

- 숫자, 문자, 날짜 데이터들을 형변환하는 함수

  - to_number - NUMBER 서식을 가진 VARCHAR를 NUMBER
  - to_char - NUMBER, DATE -> 원하는 포맷의 VARCHAR
  - to_date - 날짜 서식을 가진 VARCHAR 를 DATE

  <br>

  ``` SQL
  --		to_char			to_date
  -- 숫자	----->	문자	----->	날짜
  -- NUMBER <-----  VARCHAR <---- DATE
  --		to_number		to_char
  ```

  <br>

  

- 숫자 서식 문자

  - 0 : 숫자가 들어갈 자리를 확보한다, 남는 자리는 0(숫자 0) 으로 LPAD 한다.
  - 9 : 숫자가 들어갈 자리를 확보한다, 남는 자리는 ' '(빈 칸) 으로 LPAD 한다.
  - . : 소수점 구분 문자 추가 (정수부.소수부)
  - , : 자릿수 구분 문자 추가
  - L : 세계 통화기호 추가 (설정된 통화를 따라감, 한국 : ￦ 일본 : ￥ 등)
  - $ : 달러의 통화기호인 $ 추가

- 날짜 형식 지정 문자

  - 년, 월, 일 관련 문자
    - SCC : 세기
    - YEAR, year, Year : 영문 년도
    - YYYY, YY, YYY, Y : 숫자 년도, Y의 개수는 년도를 표현하는 자릿 수
    - MM : 숫자 월
    - MONTH, MON : 문자 월
    - Q : 쿼터, 분기
    - DD : 월 기준 날짜
    - D : 주 기준 날짜(일요일부터 1, 토요일 7)
    - DDD : 년 기준 날짜
    - DAY : 요일
    - DY : 요일 약자
  - 시, 분, 초 관련 문자
    - HH : 12시간 표기법 시간
    - HH12 : 12시간 표기법 시간
    - HH24 : 24시간 표기법 시간
    - MI : 분
    - SS : 초
    - FF : 밀리초
    - AM, PM, A.M, P.M : 오전/오후

- 오라클 날짜 대표 자료형

  - DATE : 초단위까지 표현 가능
  - TIMESTAMP : 밀리초단위까지 표현가능

- 현재 시간 함수

  - sysdate : DATE타입으로 표현한 현재 시간
  - systimestamp : TIMESTAMP 타입으로 표현한 현재 시간
    - FF 를 사용하려면 systimestamp 를 사용해야한다.


<br><br>