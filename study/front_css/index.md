---

layout: post
comments : true
title: 'FrontEnd CSS를 HTML에 적용하는 방법'
subtitle: 'CSS 정의와 기초'
date: 2020-04-13
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 81

---

> CSS, Cascading Style Sheets

<br>

- HTML, XHTML, XML 등의 마크업 언어(Markup Language)가 화면에 표현되는 방법(스타일, 모양)을 기술하는 언어
- 부모태그에 스타일을 적용하면 자식태그도 해당 스타일이 적용된다.

<br>

### CSS를 HTML에 적용하는 방법

1. 인라인(Inline) 방식
   - HTML 태그의 style속성을 이용하여 스타일을 적용하는 방법
   - 장점 : 태그를 보면서 스타일을 지정할 수 있다.
   - 단점 : 각각의 태그에 스타일을 일일히 적용해야하기 때문에 관리가 힘들어진다.
2. 임베디드(Embedded) 방식
   - head 태그 내에 style 태그를 생성하고 그 안에 작성한다.
   - CSS 선택자(Selector)를 이용한다.
   - 장점 : HTML 문서에 적용된 모든 스타일을 한번에 확인할 수 있다.
   - 단점 : 태그와 스타일이 서로 떨어져 있어서 각각 태그나 스타일만 봐서는 어떤 스타일이 적용될지 예측하기가 어렵다
3. 별도의 CSS 파일을 로드하는 방식
   - @import 코드를 이용하는 방식과 link 태그를 이용하는 방식이 있다.
   - 스타일시트를 별도의 외부파일로 생성하여 관리한다.
   - HTML 파일에서 외부 CSS 파일을 로드해서 사용한다.
   - CSS파일의 확장자는 대부분 .css를 사용한다.
   - 장점 : 스타일 목적에 맞춰서 파일을 분리할 수 있다.
   - Ex) main.css, common.css, board.css, login.css
   - 단점 : 관리 해야하는 파일이 많아진다.

<br>

### 3번(파일로드 방식) link 태그 사용 방법

``` html
<link rel=stylesheet href="./body.css" type="text/css">
```

<br>

- rel - 외부 문서의 적용방식을 지정한다.
- href - 외부 문서의 위치를 표현한다.
- type - 외부 문서 읽는 방법을 지정한다.

<br>

#### CSS를 적용시킬 때 3번 방법을 많이 사용하는데 @import 보다 link 태그 방식을 사용하는 것이 좋다.

#### link 태그 하나 당 CSS파일 하나를 로드하도록 작성한다.


<br><br>