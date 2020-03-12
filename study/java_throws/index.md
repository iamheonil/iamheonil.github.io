---

layout: post
comments : true
title: '자바의 Throws'
subtitle: '예외 떠넘기기, 예외 미루기'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 26

---

>  Throws, 예외 떠넘기기, 미루기



```java
throws 예외클래스명;

```



[접근제한자] [식별자] [리턴타입] 메소드명(매개변수) throws 예외클래스명 {

// 예외 발생 코드 포함 작성

}

- throws 가 적용된 메소드를 호출할 때 try - catch 구문을 이용한 예외처리가 필요하다.
- 예외처리를 하지 않으면 대부분 문법에러가 발생한다.



사용자 정의 예외 만들기

-  API Exception 클래스들 이외에 추가적으로 예외 상황을 정의하는 클래스를 만드는 것.
-  개발자가 직접 예외 상황을 설정하고 클래스로 구현하는 것
-  Exception 클래스, RuntimeException 클래스를 상속받아 구현한다.

```java
class User { 

	private int age;
	
	public int getAge() {
		return age;
	}

	public void setAge(int age) throws UserAgeException {
		
		if(age < 0 || age > 150) { // UserAgeException
			throw new UserAgeException();
		}
		
		this.age = age;
		
	}
	
}

// 사용자 정의 예외 클래스
//class UserAgeException extends Exception {			// Checked
class UserAgeException extends RuntimeException {	// UnChecked
	
	@Override
	public String getMessage() {
		return "나이는 0보다 작을 수 없고, 150보다 클 수 없습니다.";
	}
}

public class Exception11_CustomException {
	public static void main(String[] args) {

//		throw new UserAgeException();
		
		User user = new User();
		
		
//		user.setAge(10);
		
		
		try {
			user.setAge(1111);
		} catch (UserAgeException e) {
			e.printStackTrace();
		}
		
	}
}

```




<br><br>