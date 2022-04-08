---

layout: post
comments : true
title: 'jQuery 라이브러리를 이용한 Ajax 사용 방법에 대하여'
subtitle: ''
date: 2020-06-10
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 146

---

> jQuery 라이브러리를 이용한 Ajax 사용 방법에 대하여

<br>

- XHR 객체를 이용한 순수 자바스크립트 AJAX 는 크로스 브라우징이 지원되지 않는다
- XHR 객체를 이용한 코드 작성이 불편하다
- jQuery Ajax API 는 크로스 브라우징이 지원된다
- jQuery DOM을 이용하여 응답데이터를 손쉽게 적용할 수 있다

<br>

### jQuery Ajax API 종류

- $객체.load(url, [data] [complete]);
- $객체.get(url, [data] [success] [dataType]);
- $객체.ajax(url, [settings]);
- $객체.ajax(settings);

<br>

#### jQuery Ajax API 01 - $객체.load();

- $객체.load(url, [data] [complete])

  - AJAX 요청의 결과로 받은 응답 데이터를 지정된 객체에 곧바로 적용한다

  - 주로 응답데이터는 HTML 형식의 데이터가 필요하게 된다

  - AJAX 요청 처리 후에 추가적인 기능을 complete 속성에 Callback 함수로 적용한다

  - url - AJAX 통신을 수행할 URL, 뒤에 '?' 와 함께 쿼리스트링을 붙여 GET Method 통신으로 사용된다.

  - data - AJAX 통신에 사용할 전달 파라미터, JSON Object 타입과 String 타입 사용이 가능하다

    - JSON Object - POST 방식으로 처리할 때
    - String - Get 방식으로 사용할 때

  - complete - 요청 완료 후에 추가 작업을 수행할 callback 함수 지정

    - 콜백 함수의 유형

      ``` java
      function (
      	String responseText // 응답 데이터
       ,String textStatus // 응답 상태 메시지
       ,jqXHR jqXHR // XHR 객체를 jQuery 객체로 변환한 것
      )
      ```

      <br>


<br>

#### jQuery Ajax API 02 - $객체.get();

- $.get(url, [data] [success] [dataType])

- $.post(url, [data] [success] [dataType])

  - GET(POST) 메소드를 이용하여 AJAX 요청을 보내고 응답을 받는다.

- url

  - AJAX 통신을 수행할 URL

- data

  - 전달 파라미터 JSON Object, String 사용가능

- success

  - 요청에 대한 응답이 성공적일 경우 호출되는 콜백 함수

  ``` java
  function (
  	Object data // 응답 데이터
     , String textStatus // 응답 상태 메시지
     , jqXHR jqXHR // jQuery XHR 객체
  )
  ```

  <br>

- dataType

  - 응답 메시지의 데이터타입
  - 응답 받은 데이터를 지정한 속성값의 데이터타입으로 추출(파싱)한다
  - "xml" | "json" | "script" | "text" | "html"
    - 주로 json, html 을 사용하게 된다.

<br>

#### jQuery Ajax API 03 - $객체.ajax();

- $.ajax(url, [settings])
- $.ajax(settings)
- settings 는 AJAX 통신 설정 옵션
- settings 옵션들 중에 url 이 포함되어 있어야한다

<br>

- settings 옵션들(아래의 6개 옵션은 무조건 넣어서 사용하는 것이 좋다)

  - type

    - 요청 메소드
    - "GET" (기본값) | "POST"

  - url

    - AJAX 통신 요청 URL
    - String 타입으로 설정

  - data

    - 요청 파라미터
    - JSON Object, String, Array 타입

  - dataType

    - 응답 데이터의 처리방식
    - 응답 데이터를 지정한 형식으로 파싱한다
      - "xml" | "json" | "script" | "text" | "html"
      - 서버로부터 받은 응답데이터와 dataType 에 지정한 형식이 불일치하면 $.ajax() 메소드는 에러가 발생한다.

  - success

    - 요청/응답 성공 시 호출되는 콜백 함수

      ``` java
      function() {
          Anything data // 응답 데이터
         ,String textStatus // 응답 상태 메시지
         ,jqXHR jqXHR // jQuery XHR 객체
      }
      ```

      <br>

  - error

    - 요청/응답 실패 시 호출되는 콜백 함수

      ``` java
      function () {
          jqXHR jqXHR // jQuery XHR 객체
         ,String textStatus // 응답 상태 메시지
         ,String errorThrown // 발생한 에러의 정보
      }
      ```

    <br>

  - 아래는 필수는 아니다.

    - async

      - 비동기 처리 설정
      - true (기본값, 비동기) | false

    - beforeSend

      - Ajax 요청 전 처리할 기능을 작성할 수 있는 콜백 함수

      ``` java
      function() {
          jqXHR jqXHR,
          Object settings
      }
      ```

      <br>

    - complete

      - 응답 완료 후 처리할 기능을 작성할 수 있는 콜백 함수
      - Ajax 성공/실패에 상관없이 무조건 호출되는 함수

    - method

      - "GET" | "POST" | "PUT" | "DELETE" |
      - RESTful 요청 메소드를 지정할 수 있게 해주는 옵션들

    - statusCode

      - 응답 상태 코드에 따라 처리함수를 각각 지정할 수 있게 만들어주는 옵션
      - JSON Object 형식으로 설정함

      ``` java
      statusCode: {
          404: function() {
              
          },
          
          405: function() {
              
          },
          
           500: function() {
              
          }
      }
      
      // 이런 방식은 많이 쓰이지는 않고
      // 오류페이지 하나만 만들어 오류가 발생했다고 출력하는것이 효과적이다.
      ```

      

<br>



#### jQuery Ajax API 04 - $객체.ajax();
보강
<br><br>