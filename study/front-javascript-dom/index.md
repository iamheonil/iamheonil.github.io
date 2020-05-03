---

layout: post
comments : true
title: 'FrontEnd JavaScript DOM'
subtitle: 'JavaScript Document Object Model'
date: 2020-05-03
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 105

---

> DOM, Document Object Model

<br>

- 문서 객체 모델
- document 객체를 통해 관리된다.
- document 객체는 window 객체의 내장 객체 중 하나
- HTML 문서의 body 태그의 내용 요소들을 다룰 수 있다.
- 자바스크립트 코드로 HTML 문서의 요소(태그)들에 접근하고 관리할 수 있게 해주는 객체 모델

<br>

- DOM 관련 용어
  - 요소 (Element)
    - HTML 문서 내의 태그
  - 문서 객체(Document Object)
    - 자바스크립트 코드를 이용하여 요소에 접근할 수 있도록 객체화한 것
    - HTML요소와 자바 스크립트코드의 연결 지점(인터페이스)

<br>

- DOM 트리(tree)
  - 모든 문서 객체들을 트리구조로 표현한 것
  - 모든 요소들을 계층적 구조인 트리 구조로 저장해둔 것

<br>

- 노드(Node)
  - DOM 트리의 구성 요소
  - 요소 노드 - 태그
  - 텍스트 노드 - 태그가 감싸고 있는 텍스트
    - h1> Hello </h1
      - h1 -> 요소노드
      - "Hello" - 텍스트 노드

<br>

- DOM 객체를 사용하는 코드 적용 방법

  - document 객체는 body 태그의 모든 계층구조(태그들의 관계)를 파악해서 DOM트리를 완성시킨 이후에 사용해야 한다.

  - DOM 트리가 완성되는 시점까지 document 객체를 사용하는 코드가 실행되지 않도록 코드 실행 시점을 미뤄야 한다.

    

  - 방법 1.

    - body 태그의 끝부분 바로 위에 스크립트 태그를 작성하여 사용한다.

  - 방법 2.

    - head 태그 내 스크립트 태그에서 window.onload 를 만들어 사용한다.

  - 방법 3.

    - 일반 함수로 document 객체를 사용하고 해당 함수를 태그요소의 이벤트리스너로 사용(등록)하기

<br><br>