---

layout: post
comments : true
title: 'FrontEnd CSS에서 사용하는 색상'
subtitle: '색상의 종류와 단위'
date: 2020-04-15
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 82

---
> CSS 색상 단위

<br>

- 색상 이름
  - 영문 표기
    - black, red, blue, gray, green...
  - RGB
    - RED, GREEN, BLUE 세가지 색상의 조합(빛의 삼원색)으로 표현하는 방식
    - R, G, B에 해당하는 각 값을 0~255 또는 0%~100%로 표현
    - RGB(R, G, B) 로 표현한다.
    - rgb(100%, 0%, 100%) -> 마젠타
  - RGBA
    - RGB + Alpha 의 약자이며 투명도(Transparent)가 추가 된 것.
    - 투명도를 0.0(투명) ~ 1.0(불투명) 의 수치로 표현한다.
    - rgb(0, 255, 255, 0.5) -> 반투명 Cyan(옥색, 청록색)
    - rgb(r, g, b, a) / rgba(r, g, b, a) 둘 다 상관없이 값만 넣어준다면 알맞게 적용된다.
  - 16진수 표현법, Hexadecimal
    - RGB에 해당하는 각 수치를 16진수로 붙여서 한번에 표현한 것
    - #RRGGBB 형식으로 표현한다.
    - #RGB 형식으로 축약해서 표현 가능하다
    - 같은 숫자 두개를 한 개로 줄여서 표현할 수 있다
    - RR-> R, GG -> G, BB -> B
    - EX) RGB(255, 255, 0) == #FFFF00 == #FF0 == YELLOW
  - HSL
    - Hue, Satulation, Lightness
    - 색조, 채도, 명도
      - 색조, Hue : 0 - 360, 색 각도
      - 0 또는 360 : RED
      - 120 : GREEN
      - 240 : BLUE
      - 채도. Satulation : 0% - 100%
      - 0% : 무채색, 회색 빛
      - 100% : 유채색, 본연의 빛
      - 명도, Lightness : 0% - 100%
      - 0% : 어두움, Black
      - 100% : 밝은, White
      - 약 50%가 적당한 명도
  - HSLA

<br>

> 웹 안전 색상, Web Safe Color

<br>

- RGB 기준으로 표현 가능한 색상의 조합은 16,777,216 가지이다.
- Red가 표현 할 수 있는 색상의 범위는 0~255, 총 256가지인데 Green, Blue 모두 똑같이 256가지이다. 따라서 RGB로 조합 가능한 표현 수는 256 * 256 * 256 = 16,777,216
- RGB 표현의 모든 색상을 웹에서 나타내기에는 현실적으로 어렵다.
- 색상을 간소화하여 웹 표준 안전 색상을 정한 것이다.
- 운영체제, 브라우저, 장치 등에 구애받지 않고 표현 가능한 색상들을 정한 것
  - 0 ~ 255 를 00, 33, 66, 99, cc, ff 만 사용한다.
  - 256가지 표현을 0, 3, 6, 9, c, f 로 줄여서 사용 가능하다.
  - 6 * 6 * 6 = 216가지 색상이 된다.
  - ex) #ccc, #f36, #369

<br><br>