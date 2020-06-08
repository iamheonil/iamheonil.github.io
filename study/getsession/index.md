---

layout: post
comments : true
title: 'getSession 메소드'
subtitle: ''
date: 2020-06-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 143

---

> getSession() 메소드 두가지

<br>

- getSession()
  - HttpSession : 객체가 이미 존재할 경우 현재 HttpSession 객체를 반환
  - HttpSession : 객체가 존재 하지 않으면 (첫 접속이면) 새로운 세션 객체를 만들어서 반환한다.
- getSession(boolean create)
  - true : getSession() 과 똑같은 동작(없으면 새로 생성)
  - false : HttpSession 객체가 존재하지 않으면 Null 을 반환한다.

<br>

예를 들어 BoardWriteController (게시글 작성 컨트롤러) 를 개발하는데,

``` java
if(req.getSession(false) == null) {
    // 세션 정보가 없으면 게시글을 작성하지 못하도록 막기
    resp.sendRedirect("/board/main");
    
    // 자바코드 중단시키기
    return;
}
```

<br><br>