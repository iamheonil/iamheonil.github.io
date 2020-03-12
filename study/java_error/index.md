---

layout: post
comments : true
title: '프로그램 개발 오류(Error)'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 23

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
		
		c03.print(123);> 프로그램 개발 오류, Error

<br>

1. 컴파일 타임 에러 (Compile-time Error)

   - 컴파일 시점에 발생하는 에러

   - 이클립스에서는 소스코드를 저장하는 즉시

   - 주로 문법 에러(Syntax Error)

     

2. 런타임 에러 (Runtime Error)

   - 프로그램 수행 중 발생하는 에러

   - 수행할 수 없는 작업을 시도할 때 발생

   - 주로 Exception(예외) 처리 된다.

     - NullPointerException : null 값을 참조해서 코드 수행 시
     - ArrayIndexOutOfBoundsException : 배열에 Index 지정을 잘못 했을 때
     - ArithmeticException : 불가능한 산술연산 수행 시

     

3. 논리 에러 (Logical Error)

   - 프로그램이 에러없이 잘 작동한다.
   - 프로그램의 흐름, 동작이 개발자의 의도대로 수행되지 않을 때
     - ex) 무한루프



<br>

> Throwable 클래스

- 에러와 예외 클래스의 부모 클래스



Throwable 클래스의 계층구조

```java
Object
   |
   |
Throwable --------------|
   |					|
   |					|
 Error				Exception
(Critical Error)		 | --------------- |
    			여러 Exception		Runtime Exception
		   		(Checked Exception)			|
   									   	    |
	    								여러 Exception
    									(UnChecked Exception)
```



- Error

  - 복구 불가능한 심각한 에러

    

- Checked Exception

  - Exception의 하위클래스들 중 RuntimeException의 하위클래스를 제외한 것.

  - 반드시 예외처리 구문(Try - Catch)으로 예외 처리를 해야만 하는 클래스

    - 예외처리하지 않으면 컴파일 에러가 발생한다.

  - 코드 작성단계에서 미리 체크해서 예외처리구문을 작성해야 한다.

    - IOException, SQLException 등이 있다.

    

- UnChecked Exception

  - RuntimeException의 하위 클래스
  - 반드시 처리하지 않아도 되는 예외
  - 프로그램 실행도중 예외가 발생하면 결과를 보고
    - 예외가 발생하지 않도록 코드를 수정
    - 예외처리 구문을 작성하여 처리되도록 수정
      - NullPointerException, IndexOutOfBoundsException 등





<br>

<br>

> Error 클래스, 에러

- 심각한 수준의 오류를 뜻한다.
- 복구가 불가능하다.
- 프로그램이 무조건 중단된다.
- 시스템에 변화를 주어 문제를 해결해야한다.
- 프로그램 자체가 해결이 불가능한 수준의 문제.
  - ex) OutOfMemoryError



<br>

<br>

> Exception 클래스, 예외

- 프로그램의 예외적인 상황
- 개발자가 Exception 을 예측하여 프로그램 로직으로 처리가능한 수준의 오류
- 논리적으로 예상 가능했던 상황
- 미리 예외 상황을 처리해줘야 한다.
  - Exception Handling
    - Try, Catch 구문을 이용





```java
package kh20200312;

public class Exception01_Basic {
	public static void main(String[] args) {

		// IndexOutOfBoundsException
		int[] arr = new int[5];
		System.out.println(arr[4]);
//		System.out.println(arr[5]);

		// NullPointerException
		int[] arr2 = new int[5];
		System.out.println(arr2[4]);
		arr2 = null;
//		System.out.println(arr2[6]);

		System.out.println("\n와일문 가즈앙\n");
		int i = 0;
//		while(true) {	// 무한루프
//			arr[i] = i + 1;
//		
//		System.out.println(arr[i]);
//		System.out.println(i + "번째 완료");
//		
//		i++;
//		
//		}

		while (true) { // 무한루프를 해결

			if (i < 0 || i >= arr.length) {
				System.out.println("\n인덱스는 " + arr.length + "보다 작아야 합니다.");
				
				break;
			}

			arr[i] = i + 1;
			System.out.println(arr[i]);
			System.out.println(i + 1 + "번째 완료");

			i++;

		}

	}
}
```



<br>

- 예외 발생 시 체크사항

  1. 예외 클래스 이름

     - java.lang.ArrayIndexOutOfBoundsException
       - 배열의 인덱스를 벗어나서 접근하려고 할 때 발생한다.
         - UnChecked Exception

     

  2. 발생 지점

     - at kh20200312.Exception01_Basic.main(Exception01_Basic.java:20)

     

  3. 에러 메세지

     - 5번


<br><br>