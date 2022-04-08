---

layout: post
comments : true
title: '[Spring] Maven'
subtitle: ''
date: 2020-07-18
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 157

---
> Maven , 메이븐

<br>

- 빌드 (Build) 관리 도구
- 자바 프로젝트의 빌드를 자동화 해주는 툴
- 프로그램 개발 라이프 사이클
  소스코드 작성 -> 컴파일 -> 바이트코드 -> 빌드 -> 배포 -> 실행
- 프로그램이 실행될 때 필요한 라이브러리들을 관리해주는 툴
  - Ant
  - Maven
  - Gradle

<br>

빌드, Build

작성된 코드와 라이브러리 코드를 연결해서 실제 동작한 코드로 만드는 것

<br>

- pom.xml 설정 파일(Project Object Model)
  - 프로젝트에서 관리할 라이브러리에 대한 정보를 입력해두는 설정파일
  - 프로젝트의 정보를 입력해놓는다
  - 사용할 라이브러리의 정보도 입력해놓는다
  - 추가하려는 라이브러리를 &lt;dependency> 태그를 이용하여 설정한다
  - <a href="https://mvnrepository.com" target="_blank">메이븐 리포지토리</a>
  - 추가 라이브러리들을 받아놓은 로컬 저장소는 Libraries - Maven Dependencies 를 확인하면 된다

<br>

- 메이븐 충돌(에러) 발생한 상황 대처방법
  - 프로젝트 내에 파일 중에서 빨간색 느낌표 아이콘이 붙어있을 때
  - 서버 시작 시 이클립스 콘솔에 예외 메시지 중에서 invalid LOC header 라는 문ㄴ구가 보일 때
  - 위 두가지 상황은 메이븐 에러 상황이라고 판단할 수 있다
  - 에러가 난 라이브러리 저장소 폴더를 삭제하고 메이븐 업데이트를 수행한다
  - 에러가 난 라이브러리가 구분이 안되거나 해결이 안되면 저장소 폴더를 전체 삭제한다

<br>

- 대처 순서
  1. 이클립스를 끈다
  2. Maven Dependencies 에서 확인한 경로로 들어간 뒤, .m2\repository 폴더 삭제
  3. 이클립스를 켠다
  4. Progress 탭의 반응이 없을 때까지 기다린다 (메이븐 재구축 대기)
  5. 해결이 되지 않는다면 메이븐 문제가 아닐 가능성도 있으니 면밀히 조사해보고 그래도 해결이 안된다면 ~~프로젝트를 갈아엎어야..~~

<br><br>