---

layout: post
comments : true
title: 'FrontEnd JavaScript 자료형변환'
subtitle: 'JavaScript Type'
date: 2020-04-25
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 99

---

> MDN 자바스크립트 레퍼런스 참고하기

<br>

- 자동 형변환

<br>

```javascript
Number + Sting -> Sting 
 ex) 123 + "Hello" -> "123Hello"

Boolean + String -> String 
	 ex) true + "Hi" -> "trueHi"

Boolean + Number -> Number 
 ex) true + 5 -> 6
     true + true +5 -> 7
     (true == 1, false== 0)	
```

<br>

 - 강제 형변환

<br>

```javascript
/// 문자 -> 숫자
   parseInt( "숫자형태" )
   parseFloat ( "숫자형태" )
   Number( "숫자형태" )

/// 숫자 -> 문자
   String( 숫자 )
   숫자데이터.toString(n)
   숫자데이터.toFixed(n)
```

<br>

``` javascript
// Number 파랑
console.log(50);

// String 검정
console.log("50");

console.log("---------------------------")

// 숫자 + 문자
console.log( 50 + "50")  // -> 문자열 5050

// 문자 + 숫자
console.log( "50" + 50)  // -> 문자열 5050


console.log("---------------------------")

// Boolean +  Number
console.log( true + 123 ) // 1 + 123 = 124

// Boolean +  Boolean + Number
console.log( true + true + 123 ) // 1 + 1 + 123 =125


console.log("---------------------------")

// 문자 -> 숫자 
console.log( parseInt("50") ) // int형 50 파랑

// 숫자+문자  -> 숫자 
console.log( parseInt("123ABC") ) // "123ABC" -> 123 파랑 

//문자+숫자 -> 숫자  
console.log( parseInt("ABC123") )  //NaN, Not a number
 
// 숫자 + 문자 + 숫자 -> 숫자
console.log( parseInt("456ABC123") ) // 456 파랑

console.log("---------------------------")

// 실수 ->  정수
console.log( parseInt("123.456") ) //"123.456" -> 123(정수)

// 실수 -> 실수
console.log( parseFloat("123.456") ) //123.456 -> 123.456(실수)
```

<br>

``` javascript
// 변수선언 코드
var n1;

// 변수 값 대입
// n1 = 123; //숫자
n1 = '123'; 

console.log(n1); //보라  -> 검정 

// 변수의 선언과 동시에 초기화
var n2 = '34.789'; //문자 검정

console.log(n2); 

console.log("----------------------------------")

// 문자 ->  숫자
console.log ( Number(n1)); // 숫자 파랑
console.log ( Number(n2)); // 숫자 파랑

console.log("------------------------------")

// 문자 ->  숫자
console.log ( n1 = Number(n1)); // 숫자 파랑
console.log ( n2 = Number(n2)); // 숫자 파랑
// 원본
console.log (n1);
console.log (n2);

console.log("-----------------------------")

// 데이터 타입을 알려줌 
console.log( typeof(n1) + " : " + n1) //number : 123
console.log( typeof(n2) + " : " + n2) //number : 34.789

//위에 방식보다는 나누어서 색상까지 볼 수 있도록 하는 것이 좋다 
console.log("--------n1------------")
console.log( typeof(n1) )
console.log(n1) 

console.log("--------n2------------")
console.log( typeof(n2) )
console.log(n2) 

console.log("-------------------------------")

//진법을 지정해서 문자로 변환할 수 있다
console.log( n1.toString() ) //10진수 형태로 변환 123

console.log( n1.toString(2)) //2진수 형태로 변환 1111011
console.log( n1.toString(8)) //8진수 형태로 변환 173
console.log( n1.toString(16)) //16진수 형태로 변환 7b

console.log("-------------------------------")

// 소수점 자리수를 n개로 고정한다
console.log( n1.toFixed(2)) //소수점 2자리까지의 표현된 숫자를 문자로!
console.log( n2.toFixed(3)) //소수점 3자리까지의 표현된 숫자를 문자로!

console.log("-------------------------------")

// 123.00 -> 숫자로 형변환
console.log( Number(n1.toFixed(2))) //123 소수점이 유지되지 않는다
```

<br>

``` javascript
console.log( 100 ) //Number
console.log ( String (100)) //Number -> String 

//숫자 -> 문자  잡기술!!
//Number + String  ->  String 
// Stirng + Number ->  String 
console.log ( "" + 100)//Number -> String 
console.log ( 100 + "" )//Number -> String 

console.log("--------------------------------")

console.log("100") //String
console.log( Number("100")) // String -> Number
console.log(parseInt("100")) // String -> Number

console.log("--------------------------------")

//문자 -> 숫자 잡기술!!
//Number * Number 만 가능하기 때문에 String을 Number로 바꾼다 
console.log("100" * 1 ) // String -> Number
console.log( 1 * "100" ) // String -> Number

console.log("--------------------------------")

console.log( 10 + "20") //1020 으로 합쳐져서 나온다

//문자열을 숫자로 인식할 수 있도록 형변환해준다 Number + Number
console.log( 10 + parseInt("20")) //30 

console.log("--------------------------------")

console.log( true + "20") //Boolean -> String  true20
console.log( "10" + false) // Boolean -> String  10false 

console.log("--------------------------------")

console.log( true + 20) //Boolean -> Number 21
console.log( 10 + false) // Boolean -> Number 10

console.log("--------------------------------")

//연산 방향  왼쪽 -> 오른쪽,  앞에서 두개씩

1+2 숫자 
3+"3" 문자 
"33" + 4 문자
"334" 문자
console.log( 1 + 2 + "3" + 4 ) // 334 


"1" + 2 "12"문자
"12"+ 3 "123" 문자
"123" + 4
"1234"
console.log( "1" + 2 + 3 + 4 )  //1234
```

<br>

```javascript
//NaN, Not a Number
// 숫자로 사용하려는데 숫자가 아닐 때 반환하는 값

console.log(NaN) //숫자 보라색 
console.log( typeof(NaN))  //Number 

console.log("-------------------------")

//()안의 값이 NaN 입니까? -> 숫자가 아니죠?
// ()안의 값이 parseInt()로 변환을해서 number이 나오지 않는가? 
console.log( isNaN(123))  //false 
console.log( isNaN("ABC")) //true
console.log( isNaN("123")) //false  
console.log( isNaN("123ABC")) //true, 완벽하게 숫자만 숫자로 취급 아니면NaN 

console.log("-------------------------")

//Infinity 
// 무한대를 나타내는 키워드

console.log( 123/0 ) //Infinity
console.log( -123/0 ) //-Infinity

console.log("-------------------------")

//()안의 내용이 유한한가?
console.log( isFinite(123/0))  //false
console.log( isFinite(-123/0))  //false

console.log( isFinite(123))  //true

console.log("-------------------------")

var x = 123;
if(isFinite(x))  {//x가 유한한 값일 때만 수행

}

var y = 123;
if(!isNaN(y))  {//y가 숫자일 때만 수행
```

<br>

strict : 강력한
loose : 느슨한

자바는 강력하고, 자바 스크립트는 느슨한편이다


<br><br>