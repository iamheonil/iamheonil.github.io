---

layout: post
comments : true
title: '동적 SQL 쿼리문'
subtitle: ''
date: 2020-07-12
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 154

---

> 동적 SQL 쿼리

<br>

- 동적(Dynamic)으로 변화되어야하는 SQL 쿼리를 작성할 수 있도록 도와주는 마이바티스 태그
- &lt;select>, &lt;insert>, &lt;update>, &lt;delete> 안에서 사용한다
- &lt;if>, &lt;choose>, &lt;trim>, &lt;foreach> 태그를 제공한다

<br>

- &lt;if> 태그

  - test 속성의 값을 이용하여 조건문을 지정한다

  - test 속성의 값은 true / false 가 되도록 만들어야 한다

  - test 속성의 값은 문자열로 처리된다

  - true 나 false 가 아니면 true 로 취급되어 버린다

    - 쿼리문이 이상하면 false 처리하는 것이 아니고 그대로 실행해버리는 현상이 발생할 수 있다

  - 조건의 결과에 따라 쿼리의 추가 여부가 결정된다

    <br>

    ``` xml
    <select id="" parameterType="web.dto.Emp">
      SELECT * FROM EMP
      WHERE 1=1
      
      <if test="emp != null">
        AND empno = #{empno}
      </if>
      
    	<if test="ename != null and !ename.equals('')">
      	AND ename = #{ename}
      </if>
    </select>
    ```

    <br>

    ``` xml
    <select id="" parameterType="string">
      <!-- parameterType 이 String 일 경우 value 키워드 사용을 고려할 것 -->
    	SELECT * FROM test
      
      <if test="value == null">
      	WHERE testid = #{value}
      </if>
    </select>
    ```

    <br>

- &lt;choose>, &lt;when>, &lt;otherwise> 태그

  - if ~ else / if ~ else 구문과 비슷한 제어문 태그
  - &lt;choose> 안에 &lt;when> 태그로 조건문을 작성한다
  - &lt;when> 태그에 test 속성으로 조건문을 작성하여 else if 같은 역할을 한다
  - &lt;when> 태그 들의 마지막으로 &lt;otherwise> 태그를 사용하여 else 같은 역할을 한다

  <br>

  ``` xml
  <choose>
  	<when test="조건문1">
    
    </when>	
    
    <when test="조건문2">
    
    </when>
    
    <otherwise>
    
    </otherwise>
  </choose>
  ```

<br>

- &lt;trim> 태그
  - WHERE 절이나 UPDATE 의 SET 절에서 사용된다
  - 동적쿼리가 전달파라미터에 따라 추가되지 않는 상황에서 AND 나 OR 같은 키워드가 충돌날 수 있는 상황에서 사용한다.
  - SET 절에서는 마지막 ',' 를 고려해서 사용한다
- &lt;trim> 태그의 속성
  - prefix : 접두어 지정
  - prefixOverrides : 접두어로 설정한 값과 겹쳐지면 제거할 항목을 지정
  - suffix : 접미어 설정
  - suffixOverrides : 접미어로 설정한 값과 겹쳐지면 제거할 항목을 지정

<br>

- &lt;foreach> 태그
  - 반복되는 구문을 동적으로 생성할 때 사용하는 태그
  - 배열이나 HashMap 타입의 파라미터를 처리할 때 유용하다
  - 마이바티스의 전달파라미터는 HashMap 으로 처리하는 것이 좋다
  - 배열이나 리스트는 해시맵에 put 하여 전달한다
    - checkBox 선택 항목에 대한 조건 처리를 할 때 유용하다

<br><br>