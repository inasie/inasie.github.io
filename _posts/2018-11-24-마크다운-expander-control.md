---
title: 마크다운 - Expander control(접기/펼치기) 만들기
date: 2018-11-24
last_modified_at: 2018-11-24
categories:
- IT일반
tags:
- 마크다운
- markdown
- expander
- collapsible
- 확장
---

마크다운에서 접기/펼치기 가능한 컨트롤 문법을 알아보겠습니다. <br>
마크다운 자체엔 기능이 없는 듯 하여 html 의 details를 이용합니다.

> **마크다운**이라쓰고 html이라 읽는다

## 코드

> **INFO**<br>
div markdown="1" 은 jekyll에서 html사이에 markdown을 인식 하기 위한 코드입니다.

```html

<details>
<summary>접기/펼치기 버튼</summary>
<div markdown="1">

|제목|내용|
|--|--|
|1|1|
|2|10|

</div>
</details>
```

## 결과

<details>
<summary>접기/펼치기 버튼</summary>
<div markdown="1">

|제목|내용|
|--|--|
|1|1|
|2|10|

</div>
</details>
