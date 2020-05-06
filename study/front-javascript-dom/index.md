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
    
<br>
<br>
> DOM 객체 함수, DOM API

<br>

 + Node 생성
    + document.createElement("tagName") 요소노드 만들기
       + HTML 표준태그가 아니어도 생성됨
   + document.createTextNode("text") 텍스트노드 만들기

<br>

 + Node 추가

     + DOM객체.appendChild(대상객체)
         + DOM객체에 대상객체를 연결한다(자식으로 추가한다)
         + ex) var pTag = document.createElement("p") //p태그요소 생성
         + document.body.appendChild(pTag) //<body>에 p요소 추가
   + document.body 와 body 태그는 똑같다
     + ex) var div = document.createElement("div") //div요소 생성
     + var t = document.createTextNode("Hello") //텍스트 생성

<br>

```javascript
div.appendChild(t) //<div>에 텍스트 추가하기
document.body.appendChild(div) //<body>에 <div>추가

// document.body에 추가해야 화면에서 보임
```

<br>


 + Element 속성(Attribute) 값 다루기


     + 표준속성의 값 가져오기 (객체.표준속성)
     + 표준속성의 값 설정하기 (객체.표준속성 = "속성값")

         + ex)document.getElementById("myImg").height = 300;
         + 일반속성의 값 불러오기
           객체.getAttribute("속성명")
         + 일반속성의 값 설정하기
           객체.setAttribute("속성명", "속성값")
         + getAttribute(), setAttribute() 는 표준, 비표준 속성 모두 다룰 수 있다
         + 속성의 값은 모두 String 타입으로 정의된다

<br>

 + innerHTML 속성
     + 객체.innerHTML
     + 객체.innerHTML = "HTML양식의 문장", 객체의 자식요소가 HTML문장으로 처리된다

<br>


 + innerText 속성

     + 객체.innerText
     + 객체.innerText = "텍스트 문장", 객체의 자식요소가 텍스트문장으로 처리된다

<br>

- 내용물을 불러올 때
  - innerHTML - 태그까지 포함하여 꺼내온다
  - innerText - 태그를 제거하고 꺼내온다

* 내용물을 적용할 때
  * innerHTML - 태그를 반영하여 적용한다
  * innerText - 태그를 단순 텍스트로 적용한다 (태그가 적용되지않음)

<br>

 + Element 객체 얻기 (DOM 객체 얻기)

     + document.getElementById("ID속성값"); - 지정된 id를 가진 요소를 반환
     + document.getElementsByName("NAME속성값"); - 지정된 name을 가진 요소들을 반환
     + document.getElementsByTagName("TAG이름"); - 지정된 태그들을 반환
         + id는 HTML문서에서 유일한 값 -> getElementById 가 객체 한개만 반환
         + name속성값이나 태그이름은 중복가능 -> 객체 여러 개 반환 (배열)
         + getElementsByName, getElementsByTagName 은 선택된 요소가 1개여도 배열로 반환한다
         + Element, Elements 로 s가 붙어있는지 없는지 잘 확인하고 사용할 것!

<br>

 + Element 제거

     + 객체.remove() - 객체를 DOM트리에서 제거한다
     + 객체.removeChild(대상) - 객체의 자식노드에서 대상노드를 제거한다
+ 둘 다 화면에서 제거된다

<br>


<br><br>