---

layout: post
comments : true
title: '페이징에 필요한 데이터'
subtitle: '변수 등을 알아보자'
date: 2020-06-14
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 147

---

> 페이징에 필요한 데이터(변수 포함)

<br>

- curPage
  - current Page 의 약자
  - 현재 페이지 번호, 브라우저에서 선택한 페이지의 번호
- totalCount
  - 총 게시글 수
  - DB에서 조회된 전체 행의 수
- listCount
  - 한 페이지 당 보여질 게시글의 수
  - 직접 설정할 수 있게 만든다
- totalPage
  - 총 페이지 수
  - 전체 목록을 표현하기 위해 필요한 총 페이지 수
  - 계산으로 알아낸다
- pageCount
  - 한 화면에 출력될 페이지네이션의 개수
  - 직접 설정할 수 있게 만든다
- startPage
  - 화면에 보이는 페이지네이션의 시작 번호
  - 계산으로 알아낸다
- endPage
  - 화면에 보이는 페이지네이션의 끝 번호
  - 계산으로 알아낸다
- startNo
  - 화면에 보여지는 게시글의 시작 번호
  - 계산으로 알아낸다
- endNo
  - 화면에 보여지는 게시글의 끝 번호
  - 계산으로 알아낸다

<br>

### 페이징 1단계

- totalCount
  - 총(전체) 게시글 수
  - DB에서 TABLE을 조회하여 알아낸다
  - 검색어를 추가하거나 필터링 처리를 했을 때도 고려해야 한다
- listCount
  - 한 페이지 당 보여질 게시글의 수
  - 직접 설정한다
  - 기본값을 설정해두고 사용한다
- totalPage
  - 총 페이지의 수
  - totalPage = totalCount / listCount;
    if(totalCount % listCount > 0) totalPage++;
- 추가 작업(보정값 설정)
  - 현재 페이지(curPage)의 값이 총 페이지(totalPage)보다 크게 입력되는 경우 강제로 마지막 페이지로 고정시킨다.
  - if(curPage > totalPage) curPage = totalPage;

<br>

### 페이징 2단계

- pageCount
  - 한 화면에 출력될 페이지네이션 개수
  - 직접 입력해서 설정한다
  - 기본값을 설정해서 사용한다
  - 페이징 넘버링 방식
    1. 현재 페이지를 기준으로 앞, 뒤 특정 페이지들을 보여주기 - 구글
    2. pageCount 만큼 고정된 개수의 페이지를 보여주기 - 인벤
  - startPage = ( (curPage-1)/pageCount) * pageCount + 1;
- 추가 작업 (보정값 설정)
  - 계산된 끝 페이지번호(endPage)가 총 페이지수(totalPage)보다 더 클 때
  - 강제로 끝 페이지번호(endPage)를 총 페이지수(totalPage)로 고정한다
  - if( endPage > totalPage ) endPage = totalPage;
  - startNo
    - 현재 페이지의 게시글 시작번호 (rownum 으로 판단)
      - startNo = (curPage - 1) * listCount + 1;
    - 현재 페이지의 게시글 끝번호 (rownum 으로 판단)
      - endNo = curPage * listCount;

<br>

### 페이징 3단계

- JSP 화면에 페이지네이션으로 변수(데이터) 적용하기

<br><br>