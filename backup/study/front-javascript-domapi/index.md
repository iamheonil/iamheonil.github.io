---

layout: post
comments : true
title: 'FrontEnd JavaScript DOM API'
subtitle: 'JavaScript DOM의 API'
date: 2020-05-03
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 106

---

> DOM 객체 함수, DOM API

<br>

- Node 생성
  - document.createElement("tagName")
    - 요소노드 만들기
    - ** HTML 표준 태그가 아니어도 생성된다.
      - h1, h2 등 표준태그가 아닌 test 같은걸 넣어도 생성된다.
  - document.createTextNode("Text")
    - 텍스트 노드 만들기

<br>

- Node 추가
  - DOM객체.appendChild(대상객체)
    - DOM 객체에 대상객체를 연결한다(자식으로 추가해준다)
    - ex) 
      - var pTag = document.createElement("p") : p태그 요소 생성
      - document.body.appendChild(pTag) : body 태그에 pTag 요소 추가
      - ** document.body 와 body 태그는 똑같다.
    - ex2)
      - var div = document.createElement("div") :  div 요소 생성
      - var t = document.createTextNode("Hello") : 텍스트 생성
      - div.appendChild(t) : div 에 t 텍스트요소 추가하기
      - document.body.appendChild(div) : body 에 div 요소 추가하기
      - ** document.body에 추가해야 body 에 추가되어 화면에 출력된다.

<br><br>