---

layout: post
comments : true
title: 'FrontEnd jQuery'
subtitle: 'jQuery 입문'
date: 2020-05-07
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 110

---

> jQuery 

<br>

- 자바스크립트의 DOM을 쉽게 사용하기위해 만들어진 라이브러리
- 순수 자바스크립트 코드보다 효율적이고, 코드 생산성이 향상된다.
- HTML 노드, 스타일, 속성, 이벤트 등을 다룰 수 있다.
- CSS 선택자(Selector)를 이용하여 DOM 객체를 관리한다.

<br>

## [jQuery 홈페이지](https://jquery.com)<br>

### [jQuery 다운로드](https://jquery.com/download/) <br>

- 다운로드 경로 클릭 후, compressed Ver, uncompressed Ver 둘 중 마음에 드는 것으로 클릭하고 우클릭 - 다른 이름으로 저장을 이용하여 저장하면 된다.

<br>

- 적용하기(head에 아래의 코드 추가하기)

<br>

``` javascript
<!-- 서버가 가지고 있는 파일을 이용한 jQuery Lib 설치(배포) -->
<script type="text/javascript" src="../resources/js/jquery-3.5.1.js">
```

<br>

- jQuery 주요 기능
  - jQuery DOM
    - DOM 모델(객체) 다루는 긴으
  - jQuery Event
    - Event를 다루는 기능
  - jQuery Ajax
    - 비동기통신(Ajax)를 다루는 기능
  - jQuery Effect
    - 효과(애니메이션 등)
  - jQuery Plugin
    - 추가기능

<br>

- jQuery 버전별 특징
  - 1.x
    - 다양한 브라우저에 호환되도록 만들어진 버전(크로스 브라우징)
    - 최대한 많은 브라우저에서 호환되도록 하는 게 목적인 버전
    - 브라우저의 특성에 맞는 고유한 동작을 생략시킨 경우가 많다.
    - 소스코드의 양이 많아져 라이브러리 파일의 용량이 큰 편이다.
  - 2.x
    - 성능 향상, 다양한 기능들을 제공하기 위해서 IE 8 이하는 지원하지 않는다.
    - 옛날 브라우저에 맞춘 코드를 버리고 경량화, 성능 개선
    - 새로운 기능도 추가함
  - 3.x
    - 2.x 버전의 업그레이드 버전
    - jQuery Migrate 버전은 1.x 의 업그레이드 버전

<br>

- CDN, Content Delivery Network
  - 자주 사용되는 컨텐츠(자료파일, 이미지, 라이브러리 파일 등등)를 네트워크 중간중간에 컨텐츠서버를 두고 복사해준다.
  - 클라이언트 요청을 받으면 적절한 위치의 컨텐츠 서버와 통신하게끔 만들어주는 시스템
  - 컨텐츠(자료)들을 효율적으로 전달하기 위해 미리 준비해놓은 네트워크
  - 주로 10MB 이상의 파일(자료)들을 가져왔지만 최근에는 크기와 상관없이 사용한다.
  - 클라이언트의 컨텐츠 요청으로 발생하는 서버의 병목현상을 해결한다.
  - 서버의 불필요한 트래픽을 줄이고 반복작업을 줄여준다.

<br>

- jQuery 2.2.4 min 버전 CDN

``` javascript
<script src="https://code.jquery.com/jquery-2.2.4.min.js" integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44=" crossorigin="anonymous">
  </script>
```

<br><br>