---
title: 마크다운 - line chart 그리기
date: 2018-11-24
last_modified_at: 2018-11-24
categories:
- 프로그래밍
tags:
- 마크다운
- markdown
- 라인차트
- linechart
- chart.js
---

<canvas id="line-chart" width="600" height="800"></canvas>

<script>
var ctx = document.getElementById("line-chart");
var myLineChart = new Chart(ctx, {
    type: 'line',
    data: [
        {
            x: 10,
            y: 20
        },
        {
            x: 15,
            y: 10
        }
    ],
    options: {
        label: "라인 차트 테스트",
    }
});

</script>