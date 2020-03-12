---

layout: post
comments : true
title: '자바의 Generic'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 22

---

> 일반화 프로그래밍, 제네릭
>
> 자바에서는 일반화 프로그래밍 이라는 용어는 많이 사용하지 않고 제네릭이라고 한다. 
>
> 일반화 프로그래밍은 C언어 쪽에 더 가깝다.



* 일반화 프로그래밍

  * 자료형을 일반화시켜 프로그래밍 하는 것
    * int
    * double
    * float
    * boolean
    * String(참조형 포함)
    * Point
    * Person
    * .. 등등
  * 위의 자료형들의 특성을 무시하고 데이터타입의 이름을 정해 일반화하고 개발하는 것

  



자바에서는 제네릭을 이용하여 구현한다.

```java
// ex)

public void out (String var) { }
public void out (Integer var) { }
public void out (Boolean var) { }

// 세개를 오버라이딩하는데 내용이 매우 흡사하다.
// 이럴 때 제네릭을 사용한다.
// 중복코드를 줄여주고 재사용성이 커진다.

public <T> void out (T var) { }
```



```java
// 타입을 지정하지 않고 구현한다면 Object로 사용된다.
		List list = new ArrayList();
		
		// 부모인 List<String> 과 자식인 ArrayList 의 자료형이 다르다면 에러가 발생한다.
		// 무조건 같게 써줘야 한다
		List<String> sList = new ArrayList<String>();
		// 혹은
		List<String> sList = new ArrayList<>();
		
		sList.add("HELLO");
```



```java
List<Integer> iList = new ArrayList<>();
		// List<Int> iList = new ArrayList<>(); 는 사용 불가
		// Wrapper 클래스를 사용해야 한다.
```



타입 안정성
* 개발자가 의도한 데이터타입으로만 사용되는 것

<br>

> 제네릭, Generic



- 클래스 또는 메소드에서 사용되는 다양한 데이터타입을 일반화 시켜서 정의하는 방법.
- 코드의 재 사용성이 높아진다.
  - 타입 안정성이 제공된다. Type-Safety
  - 객체 또는 메소드가 의도하지 않은 타입으로 사용되는 상황을 방지하는 것.
  - 개발자가 의도한 데이터타입만 사용하도록 제한하는 것
- 클래스와 메소드에 적용할 수 있다.
- 불필요한 형변환을 줄일 수 있다.

자주 사용되는 제네릭 타입 파라미터 이름

* T - Type
* E - Element
* K - Key
* V - Value
* N - Number


<br>

> Generic Class

[접근제한자] [클래스식별자] class 클래스명<TYPE1, TYPE2, ... >

타입 갯수에 제한은 없지만 대부분 한개, 두개이다.

제네릭 클래스를 이용하여 객체 생성을 할 때 타입 파라미터를 결정해주는 것이 좋다.

타입파라미터를 결정하지 않으면 Object로 처리된다.



```java
// 제네릭을 적용한 class
class Class02<T> {
	
	private T data;
	
	public T display(T data) {
		setData(data);
		
		return data;

	}

	
	public T getData() {
		return data;
	}

	public void setData(T data) {
		this.data = data;
		
	}
}

public class Generic_Class {
	public static void main(String[] args) {

		// T 라고 써 놓은 자료형을 여기서 String 으로 쓰겠다 라고 작성했다.
		Class02<String> c02 = new Class02<>();
		
		c02.setData("Grape");
		String fruit = c02.getData();
		
		System.out.println(fruit);
        
		
		// T 라고 써 놓은 자료형을 여기서 Integer 로 쓰겠다 라고 작성했다.
		Class02<Integer> c03 = new Class02<>();
		
		c03.setData(100);
		int Number = c03.getData();
		
		System.out.println(Number);
				
		
		
	}
}
```



제네릭 클래스의 변수를 선언할 때 타입파라미터를 명시하고

객체를 생성하는 코드에서는 <> 만 적어도 된다. (JDK 1.7v 이후 지원)

```java
List<String> list = new ArrayList<>();
```

<br>

> Generic Method



[접근제한자] <TYPE1, TYPE2,...> [리턴타입] 메소드명(매개변수) {

}

* 메소드 내에서 사용되는 데이터타입을 일반화시켜 정의한다
* 매개변수, 반환타입, 지역변수
* 제네릭 메소드를 호출하면서 타입파라미터를 결정해준다.
  * obj.<타입파라미터>메소드명(인자);
  * obj.메소드명(인자) -> 매개변수가 타입파라미터를 사용하고 있어야 가능





```java
// 일반 클래스
class Class03 {
	
	// 일반 메소드
	public void display(int n) { 
		// 형태만 보기 위해 코드 구현은 하지 않았다.
	}
	
	// 제네릭 메소드
	public <T> T print(T t) {
		// 반환데이터, 매개변수, 지역변수, 형변환 어디든 사용 가능하다.
		// 자료형 어디든 사용 가능하다.
		// 제네릭은 Object 의 아래에 있다.
		
		// T data = 123;
		
		// 참조형으로 취급되어 null 값을 넣어놓는다.
		T data = null; 
		
		return data;
	}
	
}

// 제네릭 클래스
class Class02_1 <T> {
	
	// 제네릭 메소드
	public <K> void display(K obj, T data) {
		// 이렇게 사용하는 경우가 거의 없어서 문법만 알고 있어도 된다.
	}
}

public class Generic_Method {
	public static void main(String[] args) {
		
		Class03 c03 = new Class03();
		
		// 타입 파라미터를 지정하지 않았는데 메소드는 이렇게 사용해도 괜찮다.
		// 자동으로 결정되었는데 제대로 결정 되었다.
		
		c03.print(123);
		
		c03.<Double>print(123.0);
	}
}
```


<br>

> Multi Generic

<br>


```java
// 타입 파라미터를 여러개 사용하는 방법.

// 멀티 제네릭 클래스
class Class04<T1, T2> {
	
	private T1 data1;
	private T2 data2;
	

// 멀티 제네릭 메소드
	public <K1, K2> K2 test(K1 data) {
		K2 result = (K2) data;
		
		return result;
	}


	public T1 getData1() {
		return data1;
	}


	public void setData1(T1 data1) {
		this.data1 = data1;
	}


	public T2 getData2() {
		return data2;
	}


	public void setData2(T2 data2) {
		this.data2 = data2;
	}
	
	
}

public class Generic_Multi {
	public static void main(String[] args) {

		Class04<Integer, String> c04 = new Class04<>();
		
		c04.setData1(123);
		c04.setData2("ABC");
		
		
		// 위의 Integer, String 선언을 한 상태여도
		// 새로 생성자를 만들어서 선언해줘도 사용하는데 무관하다.
		
		c04.<Boolean, Double>test(true);
	}
}


```

<br>

> Generic Class Member

<br>

```java
class Data<K> {

	K data;
	
}

class Class05<T> {
	
	Data d1; 			// raw, Data<K> -> Data<Object>
	
	Data<String> d2; 	// Data<K> -> Data<String>
	
	Data<T> d3; 		// Data<K> -> Data<T>, 아직 빈 칸이다.
	
}

public class Generic_ClassMember {
	public static void main(String[] args) {

		Class05<Integer> c05 = new Class05<>();
		c05.d3 = new Data<>();
		// 문법 잘 확인할 것.
		// c05.d3.data(100);
		
		// Class05의 생성자는 만들었지만 d3 의 생성자는 만들지 않았음
		// c05.d3 = new Data<>(); 추가.
		c05.d3.data = 100; // NullPointerException 발생
		
		c05.d1 = new Data<>();	// Data<K> -> Data<Object>
		c05.d2 = new Data<>();	// Data<K> -> Data<String>
		c05.d3 = new Data<>();	// Data<K> -> Data<T> -> Data<Integer>
		
	}
}
```

<br>

> Generic Extends

<br>

```java
public class Generic_Extends {
	public static void main(String[] args) {

		print(123);
		print(123.456);
		
		print("String");
		
	}
	
	public static <T extends Number> void print(T t) {
		System.out.println(t);
	}
}
```



제네릭 타입 제한하기
```java

* <T> : 어떤 타입 파라미터든지 허용하는 타입파라미터 T
* <T extends 부모클래스타입> : 지정된 부모클래스타입의 하위클래스들만 허용하는 타입파라미터 T

```

특정 클래스의 하위 클래스로만 타입 파라미터를 허용할 수 있도록 제한하고 싶을 때 사용한다.

인터페이스로 설정하는것도 가능하다.


```java

* <T extends Number> 
    * Byte
    * Short
    * Long
    * Integer
    * Float
    * Double

* String, Person, Point 등 Number 와 상속관계가 아닌 타입은 입력자체가 불가능
```

<br>

> Generic Inherit

<br>


``` java
// 제네릭 클래스 구현
class Parent<T> {
	T data;
}

// 제네릭 클래스를 일반클래스가 상속 받게 된다면
// 일반 클래스는 제네릭을 모르기 때문에 다시 Object 자료형으로 변한 상태로 상속 받는다.
class Child01 extends Parent {			// T -> Object 

	
}

class Child02 extends Parent<String> {	// T -> String
	
	
}

class Child03<K> extends Parent<K> {	// T -> K -> 
										// 상속받은 타입 파라미터의 자료형 결정을 미룬다 
	
}

class Child04<M, N> extends Parent<M> {
	N data2;
	
	// M data1 : 상속받은 제네릭 M을 이용한 멤버필드, 타입 미결정
	// N data2 : 자식 클래스의 고유한 제네릭 타입(N), 타입 미결정
	
}

public class Generic_Inherit {
	public static void main(String[] args) {

		Child03<Integer> c03 = new Child03<>();
		// Child03 은 T->K->Integer 로 변환된다.
		
	}
}
```


<br>

> Generic Interface Inherit

<br>


```java
interface Inter1<T1> {
	void method1(T1 data);
	
}

interface Inter2<T2> {
	void method2(T2 data);
	
}

class Class08<E> implements Inter1<E>, Inter2<E> {

	@Override
	public void method2(E data) {
		// TODO Auto-generated method stub
		
	}

	@Override
	public void method1(E data) {
		// TODO Auto-generated method stub
		
	}
		
}


public class Generic_Interface {
	public static void main(String[] args) {

		Class08<String> c = new Class08<>();
		
		c.method1("data");
		c.method2("data");
		
	}
}
```



제네릭 클래스, 제네릭 Inherit (Interface 포함)

- 부모 클래스(Interface) 의 타입 파라미터를 결정하면서 상속해야함.
- 부모 클래스에서 Type Parameter 를 결정하지 않으면 자식 클래스가 타입 파라미터를 처리 해야한다.
  - 타입에 대한 결정을 미룰 수 있다.
  - 자식 클래스에서 지정한 타입파라미터로 사용한다.



<br>

> 와일드 카드, Wild Card (<?>)

<br>



``` java

public class Generic_WildCard {
		
	public static void display(List<?> list) {
//	public static void display(List<? extends Number> list) {	
        					// <?> 때문에 모두 다 받지만 Number 의 속해 있는 자료형들만 받는다
//	public static void display(List<? super String> list) 	{
	
		for(Object o : list) {
			System.out.println( o );
			
		}
	}
	
	public static void main(String[] args) {
		
		List<Integer> iList = Arrays.asList(10, 20, 30);
		
		display(iList);
		
		List<String> sList = Arrays.asList("A", "B", "C");
		display(sList);
		
		Object o = null;
		Integer i = null;
		
		o = i;	// Object 는 Integer 의 부모이다.
		
		List<Object> ol = null;
		List<Integer> il = null;
		
		// ol = il; : 에러 
		// 제네릭은 자바의 기본 상속구조를 무시한다.
		// 기본원칙은 이러하지만 와일드 카드를 적용함으로써 에러를 빗겨나간다
		
	}
}

```

<br>


- 타입 파라미터에서 어떤 타입으로든 사용가능하도록 지정되는 제네릭
  - <?> : 제한 없이 어떤 타입 파라미터로든지 사용할 수 있음(지양해야 한다)
  - <? extends 상위타입>
    - 지정한 상위타입의 하위클래스로만 사용할 수 있는 타입 파라미터
  - <? super 하위타입>
    - 지정한 하위타입의 상위클래스로만 사용할 수 있는 타입 파라미터






<br><br>