---

layout: post
comments : true
title: 'FrontEnd jQuery 이벤트'
subtitle: 'jQuery Node Event'
date: 2020-05-12
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 115

---

> jQuery Event

<br>

전부 쌍으로 이루어져 있고, Deprecated 되어있다.

- bind <-> unbind
- live <-> die
- delegate <-> undelegate
- load <-> unload

<br>

지금 사용하고 있는 이벤트 리스너 등록/해제 함수는

- on / one(등록)

<br>

```javascript
$("객체").on("이벤트이름", function() {
  // 이벤트 처리코드 작성
});

$("객체").on("이벤트이름", "Selector", function() {
  // 동적으로 추가되는 객체의 부모요소에 사용한다.
  // 셀렉터 부분을 알맞게 수정해준다.
});

$("객체").on({
  "이벤트명1": function() {},
  "이벤트명2": function() {}
  // 이런식으로 여러 개의 이벤트 리스너를 한번에 등록할 수 있다.
});
```

<br>

- off(해제)

``` javascript
$("객체").off("이벤트이름");

$("객체").off("이벤트이름", "셀렉터");
```

<br>

- 이벤트 리스너 등록 함수 축약

<br>

``` javascript
$("객체").이벤트명(function() {
  // 이벤트 리스너 코드
});

// ex)
$("myDiv").on("mouseover", function() {});

// ex)
$("myDiv").mouseover(function() {});
```

<br>

- 이벤트 발생시키는 함수

<br>

``` javascript
$("객체").trigger("이벤트명")

$("객체").이벤트명()

// 매개변수 없이 이벤트 이름을 이용해서 호출하면 trigger와 같다.

// ex) #myDiv에 클릭이벤트 발생시키기
$("myDiv").trigger("click")

// ex)
$("myDiv").click()
```

<br><br>