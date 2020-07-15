---

layout: post
comments : true
title: 'MyBatis TypeAlias'
subtitle: '마이바티스 별칭 붙이기'
date: 2020-07-14
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 155

---

> MyBatis TypeAlias

<br>

- 마이바티스 쿼리 수행 태그의 속성으로 parameterType, resultType 을 설정할 때 DTO(VO) 의 패키지 까지 포함한 풀네임을 적용해야한다
- 패키지의 길이가 길어질 경우 불편함을 줄이기위해 TypeAlias 를 이용해 DTO 의 별칭을 붙여 사용할 수 있다
- 오히려 유지보수성을 떨어뜨리는 경우도 있어 조심히 사용해야 한다

<br>

### TypeAlias 적용 방법 두가지

- 마이바티스 Configuration XML 파일에서 &lt;setting> -> &lt;environments> 위에 작성해야한다, 해당 부분이 아니면 오류가 발생한다

1. 클래스 단위로 등록하기

   <br>

   ``` xml
   <typeAliases>
   		<typeAlias type="web.dto.Emp" alias="Emp" />
   </typeAliases>
   ```

   <br>

2. 패키지 단위로 등록하기

   <br>

   ``` xml
   <typeAliases>
   	<package name="web.dto"/>
   </typeAliases>
   ```

   <br>

   등록 된 패키지의 DTO 클래스의 정의코드 위에 @Alias("별칭") 을 적어주어 지정할 수도 있다

   @Alias 를 사용하지 않으면 클래스명으로 자동 정의된다

<br><br>