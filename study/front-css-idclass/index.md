---

layout: post
comments : true
title: 'FrontEnd 의 핵심 Selector(선택자)'
subtitle: 'CSS의 핵심 문법인 Selector(선택자)'
date: 2020-04-17
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

- 위의 4개의 선택자(전체, 태그, 아이디, 클래스)들이 가장 많이 사용되는 선택자이다

<br>

- 복합 선택자
  - 둘 이상의 선택자를 복합적으로 사용하는 선택자
  - 선택자에 포함된 요소들의 관계를 따져 태그들을 선택한다
    1. 하위(자손) 선택자 - Descendent
       - E F : E의 하위 요소인 F를 선택한다.
       - ex) div p { }
       - -> div 요소의 자손 중 모든 p 태그 요소
       - #board .title { }
       - -> id가 board 인 요소의 자손 중 class가 title 인 요소
    2. 자식 선택자 - Child
       - E > F : E 요소의 자식인 F 요소 전부 선택
    3. 형제 선택자 - Sibling
       - E + F : E 요소의 인접형제 F 요소 (E요소의 바로 뒤에 위치한 F요소 한 개)
       - E ~ F : E 요소의 일반형제 F 요소 (E요소의 뒤에 위치하는 모든 F요소)

<br>

``` css
h1+p {
					/* 바로 뒤에 위치한 한 개의 태그만 선택한다. */
      		background-color: yellow;
}

h1~h1 {
          background-color: green;
}

.choco + .choco {
          color: blue;
}

p + p {
         font-style: italic;
}
```

<br>

- 속성 선택자
  - 요소의 속성(Attribute)를 이용하여 선택하는 선택자
    - [attr] : attr 속성을 가지고 있는 요소를 모두 선택한다.
    - E[attr] : attr 속성을 가지고 있는 E 요소를 모두 선택
    - E[attr="val"] : attr속성의 값이 "val"과 같은 E요소를 선택
      - 띄어쓰기 포함하여 속성의 값이 완전 일치해야 선택이 된다.
    - E[attr~="val"] : attr 속성의 값이 "val"을 완전 포함하는 E요소를 선택
      - 띄어쓰기로 구분된 단어와 같은 값이면 선택이 된다.
    - E[attr^="val"] : attr 속성의 값이 "val"로 시작하는 E요소 선택
    - E[attr$="val"] : attr 속성의 값이 "val"로 끝나는 E요소 선택
    - E[attr*="val"] : attr 속성의 값이 "val"을 부분 포함하는 E요소 선택
    - E[attr|="val"] : attr 속성의 값이 "val"과 같거나 "val-"로 시작하는 E요소 선택

<br>

``` css
       /* class 속성을 가지고 있는 div 태그 요소 */
        div[class] {
            border: 1px solid green;
        }
        
        /* title 속성의 값으로 "greeting"을 가지고 있는 H1 태그 요소 */
        h1[title="greeting"] {
            border: 1px solid blue;
        }   
        
        /* title 속성의 값으로 "greeting"이라는 단어를 완전하게 포함하는 h1 태그 요소 */
        h1[title~="greeting"] {
            border: 1px solid red;
        }
        
        /* 클래스 이름 "abc"라는 단어를 포함하고 있는 h1 태그 */
        /* ~=가 아닌 =만 존재한다면 포함하고 있으면 안되고 완전하게 일치해야한다. */
        /* = 는 너무 어려우니 h1.abc 와 같은 식으로 표현하는것도 괜찮다. */
        h1[class~="abc"] {
            background: yellow;
        }
        
        /* */
        
        /* 클래스의 값이 te로 시작하는 태그 검색 */
        h1[class^="te"] {
            font-size: 100px;
        }
        
        /* 클래스의 값이 st로 끝나는 태그 검색 */
        h1[class$="st"] {
            border: 1px dotted orange;
        }
        
        /* class의 값으로 "d"를 포함하는 h1 태그 요소 */
        h1[class*="d"] {
            background: tomato;
        }
        
        /* class의 값이 abc이거나 abc- 로 시작하는 태그 요소 검색 */
        h1[class|="abc"] {
            font-size: 75px;
        }
```

<br>

- 가상 선택자
  - Psuedo Selector, 의사 선택자
  - HTML 문서에 실제 요소로는 존재하지 않는 대상을 선택한다. 이벤트 기반, 특정 순서기반 선택자가 있다.
    1. 가상 클래스 선택자 (이벤트 기반)
       - :hover : onMouseOver 이벤트에 반응하여 선택
       - :active : onMouseDown 이벤트에 반응한다
       - :link : 'a' 태그의 방문 전 상태
       - :visited : 'a' 태그의 방문 후 상태
       - :enable : 활성화(enable) 상태인 요소
       - :disable : 비활성화(disable) 상태인 요소, focus를 가질 수 있는 상태인지 판단해서 선택
       - :checked : checked 상태인 요소(Checkbox, Radiobutton)
       - :focus : onfocus 상태인 요소(포커스를 가지고 있는 요소)
       - :empty : 컨텐츠가 비어있는 요소, 자식요소가 없는 대상을 선택
    2. 가상 클래스 선택자 (순서 기반)
       - :root : 최상위 태그, html 태그를 뜻한다.
       - :nth-child(n) : 앞에서부터 n번째 요소
       - nth-last-child(n) : 뒤에서부터 n번째 요소
       - first-child : 첫번째 요소
       - last-child : 마지막 요소
       - only-child : 유일한 자식(형제요소가 없을 때)
       - only-of-type : 유일한 타입일 때(형제요소가 있더라도 단독 타입일 때)
    3. 가상 요소 선택자
       - ::before : 태그 요소의 앞에 가상요소 추가
       - ::after : 태그 요소의 뒤에 가상요소 추가
       - ::first-line
       - ::first-letter

<br>

``` css

/* 예제가 너무 길어서 KHFrontend repository Selector/Selector07,08 참고하기 */

```

<br>

- 부정 선택자

<br>

``` css
* {

}
```

<br><br>