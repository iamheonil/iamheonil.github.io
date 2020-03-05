---

layout: post
comments : true
title: '클래스다이어그램의 기본'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 7

---

> 클래스 다이어그램 <br>

프로그램 설계 시 클래스의 형태, 구조, 클래스간의 관계를 일정한 규칙과 기호등을 사용해 표현한 것. <br>
시스템의 논리적 구조를 표현한 다이어그램 <br>
** 논리적 구조 = 클래스의 구조 + 클래스들 간의 관계 <br>

```java
//======================================================================

// |===========================|	- 접근제한자 표현 기호
// |                           |	- + : public
// |         클래스 이름          |	  - # : protected
// |                           |	- ~ : default
// |===========================|	- - : private
// |                           |
// |                           |	멤버필드 표기 예시
// |                           |	private String name	=> - name : String
// |                           |	public int num;		=> + num : int
// |          멤버 필드          |	  double height		  => ~ height : double
// |                           |
// |                           |	멤버 메소드 표기 예시
// |                           | 	public String getName() { }     => + getName() : String	
// |                           |	private double out(int n1) { }	=> - display(int) : double
// |===========================|
// |                           |	- 스테레오 타입, Stereotype
// |         멤버 메소드          |	  - 특수한 기능을 수행함을 표현하는것.
// |                           |	- <<Override>> 처럼 <<기능>> 로 표현한다. 주석처럼 사용한다.
// |===========================|    
//      Class Diagram
```

<br><br>