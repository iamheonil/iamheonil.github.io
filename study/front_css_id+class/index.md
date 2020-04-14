---

layout: post
comments : true
title: 'FrontEnd 의 핵심 Selector(선택자)'
subtitle: 'CSS의 핵심 문법인 Selector(선택자)'
date: 2020-04-15
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 85

---
> id, class 속성

<br>

- Global Attribute, 공용 속성이다.
  - 모든 태그들이 다 가지고 있는 속성
- id 속성
  - HTML 문서에서 각 요소들을 구분하기 위해 사용한다.
  - HTML 문서에서 id들은 고유한 값으로 부여되어야 한다.
  - CSS를 적용하거나 JS Event 처리코드를 적용할 때 사용한다.
  - '#' 기호와 연계해서 사용한다.
- class 속성
  - 태그들을 그룹지을 때 사용한다
  - 여러 태그 요소들에게 같은 클래스 값을 적용하여 같은 그룹으로 표현한다.
  - 같은 클래스 값을 가진 태그들에게 공통적인 스타일을 적용할 수 있다.

<br>

``` html
<div class="red"> </div>
<p class="red"> </p>

<!--
-> "red"라는 이름으로 같은 스타일을 부여할 수 있다.
. 기호를 이용하여 표현한다.
띄어쓰기로 구분하여 여러 값을 부여할 수 있다.
-->
<div class="red content extra"> </div>


```

<br>

> 선택자, Selector

<br>

- HTML 문서에서 특정 요소를 선택하는 CSS 문법
- 선택한 요소들에게 일괄적으로 같은 스타일을 적용할 수 있다.

<br>

선택자의 종류

- 전체 선택자
  - 모든 태그의 기본 설정을 넣을 때 사용하는 전체 선택자
  - 브라우저가 자동으로 넣어주는 CSS를 없앨 때 사용한다
  - 해당 문서에서 사용할 기본 폰트스타일을 적용할 때 사용한다

<br>

``` css
* {

}
```

<br>

- 태그 선택자

<br>

``` css
tagName {

}
```

<br>

- 아이디 선택자

<br>

``` css
#idName {

}
```

<br>

- 클래스 선택자

<br>

``` css
.classname {

}
```

<br>

- 위의 4개의 선택자가 가장 많이 사용되는 선택자이다

<br>

#### 목요일 이후 보충예정

- 복합 선택자

<br>

``` css
* {

}
```

<br>

- 속성 선택자

<br>

``` css
* {

}
```

<br>

- 가상 선택자

<br>

``` css
* {

}
```

<br>

- 부정 선택자

<br>

``` css
* {

}
```

#### 목요일 이후 보충예정

<br><br>