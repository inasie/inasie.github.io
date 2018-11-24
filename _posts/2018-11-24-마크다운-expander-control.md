---
title: 마크다운에서 Expander control 만들기
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

마크다운에서 확장/축소 가능한 컨트롤 문법을 알아보겠습니다. <br>
마크다운 자체엔 기능이 없는 듯 하여 html 의 details를 이용합니다.

> **마크다운**이라쓰고 html이라 읽는다

## 코드

```html
<details>
<summary>확장/축소 버튼</summary>

|제목|내용|
|--|--|
|테스트1|테스트1|
|테스트2|테스트2|

</details>
```

## 결과

<details>
<summary>확장/축소 버튼</summary>

|제목|내용|
|--|--|
|테스트1|테스트1|
|테스트2|테스트2|

</details>
