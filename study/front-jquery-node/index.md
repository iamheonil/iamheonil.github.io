---

layout: post
comments : true
title: 'FrontEnd jQuery의 다양한 Node 접근 방식'
subtitle: 'jQuery Node'
date: 2020-05-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 112

---

> 다양한 노드접근 방식

<br>

- $("객체").eq(index) - index(숫자)번째 노드를 jQuery DOM 객체로 변환한다.
- $("객체").get(index) - index번째 노드를 JS DOM 객체로 반환한다.
- jQuery DOM 객체에 [index]를 적용하면 get(idx)와 같은 동작을 한다.

<br>

```javascript
$("p")[2] == $("p").get(2)
```

<br>

- 순차적으로 노드에 접근하기(반복문)

  ``` javascript
  $(객체).each(function(index, element) {
  		// 요소마다 각각 반복 될 코드
    
  })
  
  // index : 객체의 인덱스
  // element : 해당 반복의 JS DOM 객체
  
  $("p").each(function(i, e) {
  			console.log("-- " + i + " --")
  			console.log(e);
                  
  			console.log(this)
  		  console.log($(this))
  // 기본적으로 콜백함수에서 사용된 this 키워드는 해당 함수를 호출한 객체를 지칭한다.
  })
  
  
  $("p").each(function() {
  			if ($(this).is($("#stop"))) {
  		// return false; // each() 함수 종료 코드
  
  		// return; // 이번 한번만 함수 종료
  		//
  		// return false; // 이후 모든 함수 종료
  		// 콜백함수에서 return false; 로 false 값을 전달하면 콜백함수를 호출한 객체가 중단된다.
  }
  
  $(this).css("background", "tomato")
  			console.log($(this).is($("#stop")))
  
  })
  
  ```

<br>

- 객체 비교하기
  - $(객체1).is$($(객체2))
    - 객체1 과 객체2가 같은 객체인지 비교한다. (Boolean 타입으로 반환)

<br>

- 하위노드 중에서 특정 노드 찾기
  - $("객체").find("selector")
    - 객체의 하위노드에서 selector에 해당하는 객체를 반환한다.

<br>

- 자식노드 찾기 .children()
  - $("객체").children(); -> 자식노드들 전체 선택
  - $("객체").children("selector") -> 선택자에 해당한 노드 선택

<br>

- 부모노드 찾기 .parent()
  - $("객체").parent() -> 부모노드 선택
  - $("객체").parent("selector") -> 선택자에 해당하는 노드 선택

<br>

- 조상 노드 찾기 .parents()
  - $("객체").parents() -> 조상노드 찾기
  - $("객체").parents("selector") -> 선택자에 해당하는 노드 선택

<br>

- 이전 인접 형제 노드 찾기
  - $("객체").prev() -> 이전 인접형제 노드 찾기
  - $("객체").prev("selector") -> 선택자에 해당하는 노드 찾기

<br>

- 이전 모든 형제 노드 찾기
  - $("객체").prevAll() -> 이전 모든형제 노드 찾기
  - $("객체").prevAll("selector")

<br>

- 다음 인접 형제 노드 찾기
  - $("객체").next() -> 다음 인접형제 노드 찾기
  - $("객체").next("selector")

<br>

- 다음 모든 형제 노드 찾기
  - $("객체").nextAll() -> 다음 모든형제 노드 찾기
  - $("객체").nextAll("selector")

<br><br>