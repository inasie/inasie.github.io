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

<details><summary> 코드 보기 </summary>
<p>

```html
<div style="width:75%;">
    <canvas id="line-chart"></canvas>
</div>

<script>
var ctx = document.getElementById("line-chart");
var myLineChart = new Chart(ctx, {
    type: 'line',
    data: [
        labels: ['1', '2', '3', '4', '5', '6', '7'],
        datasets: [{
            borderColor: window.chartColors.blue,
            data: [
                10, 5, 20, 35, 10, 2, 56
            ]
        }]
    ],
    options: {
        responsive: true,
        title: {
            display: true,
            text: 'line chart 테스트'
        },
        tooltips: {
            mode: 'index',
            intersect: false,
        },
        hover: {
            mode: 'nearest',
            intersect: true
        },
        scales: {
            xAxes: [{
                display: true,
                scaleLabel: {
                    display: true,
                    labelString: 'Month'
                }
            }],
            yAxes: [{
                display: true,
                scaleLabel: {
                    display: true,
                    labelString: 'Value'
                }
            }]
        }
    }
});

</script>
```

</p>
</details>

## 차트 결과

<div style="width:75%;">
    <canvas id="line-chart"></canvas>
</div>

<script>
var ctx = document.getElementById("line-chart");
var myLineChart = new Chart(ctx, {
    type: 'line',
    data: [
        labels: ['1', '2', '3', '4', '5', '6', '7'],
        datasets: [{
            borderColor: window.chartColors.blue,
            data: [
                10, 5, 20, 35, 10, 2, 56
            ]
        }]
    ],
    options: {
        responsive: true,
        title: {
            display: true,
            text: 'line chart 테스트'
        },
        tooltips: {
            mode: 'index',
            intersect: false,
        },
        hover: {
            mode: 'nearest',
            intersect: true
        },
        scales: {
            xAxes: [{
                display: true,
                scaleLabel: {
                    display: true,
                    labelString: 'Month'
                }
            }],
            yAxes: [{
                display: true,
                scaleLabel: {
                    display: true,
                    labelString: 'Value'
                }
            }]
        }
    }
});

</script>