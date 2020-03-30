---

layout: post
comments : true
title: '생성자, Constructor에 대하여'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 8

---

> 생성자, Constructor <br>

### 생성자
new Overloading(); <br>
Scanner sc = new Scanner(System.in); <br>
       ↑↑↑ 생성자 ↑↑↑ <br>
객체가 생성될 때 반드시 호출되는 특수한 메소드 생성자는 객체를 초기화 한다. <br>
생성된 이후에 최초로 가져야 할 값을 지정(대입)한다.			   ] 같은 <br>
객체가 가지고 있는 멤버필드(인스턴스 변수)를 초기화 한다.	      ] 말이다. <br>
생성자를 정의하지 않는다면 디폴트 생성자를 컴파일러가 자동으로 추가한다. <br>
생성자가 하나라도 정의되어 있다면 디폴트 생성자는 당연히 없다. <br>
<br>
this 키워드
자기 참조 객체
클래스 코드에서(설계 클래스) 다른 멤버를 지칭할 때 사용한다.
주로 멤버필드와 매개변수가 같은 이름일 때 서로를 구분하기 위해 사용한다.
Setter를 사용해도 된다. 실제로 본인은 this 키워드보다 setter 키워드를 더 많이 사용한다. <br>
<br>
this() 생성자 <br>
생성자 코드에서 다른 생성자를 호출할 때 사용한다. <br>
다른 생성자에서 이미 정의 되어져있는 초기화 코드를 다시 작성하지 않고 재사용할 수 있게 된다. <br>

<br><br>