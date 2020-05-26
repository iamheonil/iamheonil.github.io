---

layout: post
comments : true
title: '요청 파라미터의 한글 인코딩처리 설정'
subtitle: 'UTF-8'
date: 2020-05-26
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 128

---

> 요청 파라미터의 한글 인코딩처리 설정하기 (UTF-8)

<br>

- 아파치 웹 서버는 인코딩을 ISO-8859-1(Latin 1)을 사용한다.
- 한글이 웹 서버를 통과할 때 ISO-8859-1 방식으로 해석을 해버린다.(이 때 한글이 깨진다.)
- 원본 데이터가 UTF-8 인코딩을 사용하므로 데이터를 사용할 때 UTF-8 형식으로 다시 합성할 필요가 있다.

<br>

#### Get 메소드 요청데이터에 대한 한글(UTF-8) 설정

- 사용중인 서버의 설정파일인 server.xml(톰캣서버 파일을 넣어놓은 폴더) 파일에서 인코딩을 설정한다.
- 사용중인 서버의 PORT 번호를 속성으로 가지고 있는 &lt;Connector>를 찾는다.
- URIEncoding="UTF-8" 속성을 직접 추가해준다.

<br>

``` java
<Connector URIEncoding="UTF-8" connectionTimeout="20000" port="8088" protocol="HTTP/1.1" redirectPort="8443"/>
```

<br>

#### Post 메소드 요청데이터에 대한 한글(UTF-8) 설정

- 요청 객체를 사용하기 전에 인코딩을 UTF-8 로 설정한다, 메소드 시작부분에 바로 넣어주는게 바람직하다.

<br>

``` java
req.setCharacterEncoding("UTF-8");
```

<br><br>