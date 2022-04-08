---

layout: post
comments : true
title: 'FrontEnd jQuery Node 명령어'
subtitle: 'jQuery Node Command'
date: 2020-05-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 113

---

> 노드의 여러가지 명령어

<br>

- $("노드텍스트");

<br>

``` javascript
$("div") // div태그 객체가 생성된다.

// $("div") - div태그 객체가 생성된다.
// $(div) - div태그 객체를 선택한다.
// 구분 잘 해야한다.
```

<br>

- $("객체").clone() - 객체를 복사하여 반환한다

<br>

``` javascript
var $div2 = $("#myDiv").clone();

// 깊은 복사(Deep Copy)로 새로운 사본이 만들어진다.
// 자식노드까지 함께 묶음으로 복사된다.
```

<br>

- 노드 이동/추가
  - $부모노드.append($추가노드)
  - $추가노드.appendTo($부모노드)
    - 부모노드의 마지막 자식으로 추가노드를 삽입한다, 이미 다른 위치에 존재하던 노드라면 이동이 된다
  - $부모노드.prepend($추가노드)
  - $부모노드.prependTo($추가노드)
    - 부모노드의 처음 자식으로 추가노드를 삽입한다, 이미 다른 위치에 존재하던 노드라면 이동이 된다.

<br>

- Before / After
  - Before
    - $("기준노드").Before($("추가노드").속성)
      - 기준노드를 기준으로 태그 이전에 추가 태그를 삽입/이동한다.
    - $("추가노드").insertBefore($기준노드)
  - After
    - $("기준노드").After($("추가노드").속성)
      - 기준노드를 기준으로 태그 이후에 추가 태그를 삽입/이동한다.
    - $("추가노드").insertAfter($기준노드)

<br>

- 노드의 내용 읽기/변경
  - $("객체").html() : 객체의 내용물(innerHTML)을 반환한다.
  - $("객체").html("태그텍스트") : "태그텍스트"로 innerHTML이 변경된다.
  - $("객체").text() : 객체의 내용물(innerText)을 반환한다.
  - $("객체").text("기본텍스트") : "기본텍스트"로 (innerText)이 변경된다.

<br><br>
<br>