---

layout: post
comments : true
title: 'FrontEnd JavaScript Event'
subtitle: 'JavaScript Event'
date: 2020-05-05
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 107

---

> JS 이벤트, JS Event

<br>

- 사용자의 모든 입력(행위)들을 프로그램에서 미리 정의해놓은 객체
- 사용자의 입력(동작) 뿐만 아니라 특정 사건도 포함한다.
- 컴퓨터(운영체제)에서 발생한 이벤트를 감지하고 해당 이벤트를 이벤트가 발생한 응용프로그램에게 전달한다.
- 전달된 이벤트는 해당 응용프로그램에서 적절한 처리를 수행한다
- 이벤트 기반 처리(Event Driven)



<br>

- 기본 이벤트
  - 태그 요소에 별도로 이벤트 처리코드를 연결하지 않아도 기본적으로 실행되는 이벤트들
    - a 태그 요소를 클릭 -> 지정된 경로로 페이지 이동(location.href = "지정경로")
    - 브라우저 화면에 마우스 우클릭 -> 메뉴 보여주기
    - form 태그 요소에서 submit 버튼 클릭 -> 액션에 지정된 경로로 데이터를 전달하며 페이지 이동 발생(form.submit())

<br>

- 주요 이벤트
  - 마우스 관련 이벤트
    - click - 마우스를 클릭했을 때
    - dblclick - 마우스를 더블 클릭했을 때
    - mousedown - 마우스 버튼을 눌렀을 때
    - mouseup - 마우스 버튼을 땠을 때
    - mousemove - 마우스 포인터를 이동했을 때
    - mouseenter - 마우스 포인터가 요소 위로 올라갔을 때
      - mouseover 와 동일, 그러나 over 는 자식 요소까지 포함해서 판단한다.
    - mouseleave - 마우스 포인터가 요소 밖으로 나갔을 때
      - mouseout 과 동일, 그러나 over 는 자식 요소까지 포함해서 판단한다.
  - 키보드 관련 이벤트
    - keydown - 키보드를 눌렀을 때(한번)
    - keyup - 키보드에서 손을 뗐을 때
    - keypress - 키보드를 눌렀을 때(연속)
      - 이벤트 발생 순서
      - 1. keydown
        2. keypress
        3. keyup
      - keypress는 alt, ctrl, shift, esc 같은 가상키에 반응하지 않는다.
      - keydown 은 모든 키에 반응 한다.
  - 폼 관련 이벤트
    - submit - 폼이 제출 되었을 때(제출 버튼을 눌렀을 때)
    - reset - 폼이 초기화 되었을 때
    - focus - 특정 요소에 입력 포커스가 들어갔을 때
    - blur - 포커스를 잃었을 때
    - change - 폼 필드(폼의 자식요소)에 변화가 생겼을 때
    - select - select 태그 요소의 항목을 선택했을 때
  - 윈도우(창) 이벤트
    - load - HTML 문서 또는 요소가 불러와졌을 때(메모리에 로드 됐을 때)
    - resize - 요소 크기(윈도우 창의 크기)가 변경 되었을 때
    - scroll - 페이지 스크롤이 이동되었을 때

<br><br>