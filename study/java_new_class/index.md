---

layout: post
comments : true
title: '클래스의 정의'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 5

---

> 클래스의 정의 <br>

클래스의 정의 <br>

접근제한자 클래스식별자 'class' 클래스명 {  
	// 멤버필드  
	// 멤버메소드<br>

}<br>

ex)

```java
public class MemberField_01 {
	// 변수선언으로 만드는 곳 스택 메모리
	// 멤버 필드
	
	private int num = 1995;
	private String name = "Heonil";
	
	public int getNum() {
		return num;
	}
	public void setNum(int num) {
		this.num = num;
	}
	
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}

}
```

접근제한자 : public, 붙이지 않음(default) <br>
public - .java 파일의 이름과 같은 클래스명일 경우 붙일 수 있다. <br>
			하나의 java 파일 안에서는 하나의 public 클래스만 정의할 수 있다. <br>
Test.java 라는 파일이면 public class Test { 만 정의할 수 있다는 말. <br>
class A, B를 만들고 앞에 public class A, B를 붙이면 에러가 표시된다. <br>
default - public 클래스 이외의 클래스에게 사용, 위의 예시라면 A, B 에 default를 붙이는게 맞다. <br>
<br>
클래스 식별자 : 클래스의 용도에 따라서 식별할 수 있도록 사용하는 키워드 <br>
abstract, final, static <br>
추상,	파이널,	정적 <br>
<br>

선언방법과 주의사항

1. 클래스명 : 첫글자를 식별자라고 하며 영어 대문자로 사용해야한다.
2. 멤버 필드 : 클래스를 구성하는 변수와 상수를 포함한다. 주로 변수로 구성된다.
3. 객체가 생성될 때마다 각각의 객체마다 변수공간을 따로 가지게 된다.
4. 멤버 메소드 : 객체의 기능이나 행위를 정의하는 코드 

<br><br>
객체 변수 선언하기 <br>
클래스명 객체변수명; <br>
		
객체 생성하기(인스턴스화) <br>
객체변수명 = new 클래스명(); <br>
		
객체의 멤버에 접근하기(참조하기) <br>
객체변수명.멤버필드명 <br>
객체변수명.멤버메소드이름(); <br>
** 참조연산자 '.' 을 이용하여 객체변수를 통해 멤버에 접근할 수 있다. <br>
묶어 놓은것, 필드와 메소드를 관리하며 프로그램이 돌아가게끔 <br>
<br>
Getter Method  <br>
멤버필드의 값을 가져올 수 있도록 만든 메소드 <br>
가져온다(읽기) <br>
메소드명을 get 으로 시작하고 멤버필드의 첫 글자를 대문자로 작성한다. <br>

public 데이터타입 getXyz() { <br>
 return 필드의 변수명; <br>
} <br>
<br>
ex) Getter Method <br>
private int num;  멤버필드 num -> <br>
public int getNum() { <br>
		return num; <br>
} <br>
<br>
Setter Method <br>
멤버필드의 값을 설정할 수 있도록 만든 메소드 <br>
쓰기 <br>
메소드명을 set 으로 시작하고 멤버필드의 첫 글자를 대문자로 작성한다. <br>
public void setXyz(해당필드의 데이터타입 필드명) { <br>
		this.필드명 = 필드명; <br>
} <br>
<br>
ex) Setter Method <br>
private int num;  멤버필드 num -> <br>
public void setXyz(int num) { <br>
				this.num = num; <br>
}<br>
<br>
클래스 내부에서 사용되는 변수의 유형 <br>
인스턴스 변수, 클래스 변수, 지역 변수 <br>
Instance Variable, Class, 	Local <br>
<br>
인스턴스 변수 <br>
객체를 인스턴스화 했을 때 인스턴스 안에 만들어지는 변수마다 공간이 따로 배정된다. <br>
<br>
클래스 변수 <br>
정적 변수라고도 하며 Static 키워드가 적용된 멤버 필드를 뜻한다. <br>
클래스 당 하나의 공간을 관리하는 변수. <br>
프로그램이 실행되기 전(Ctrl + F11 를 누른 바로 직후 - 정적인 시점)에 미리 메모리의 클래스 영역에 생성한다. <br>
해당 클래스 타입으로 생성된 객체들이 하나의 공간을 공유한다. <br>
객체를 생성하지 않아도 클래스 멤버를 사용할 수 있다. <br>
<br>
지역 변수 <br>
메소드 내에서 선언된 변수 <br>
접근제한자 사용할 수 없다. <br>
매개변수도 지역변수로 취급됨. <br>
메소드마다 별도의 공간을 가지게 된다. (스택 메모리영역), 같은 이름의 변수가 다른 메소드에 존재 가능하다. <br>
초기화하지 않으면 쓰레기 값을 가지고 있게된다. <br>

<br><br>