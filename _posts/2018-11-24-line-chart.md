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

```html
<canvas id="line-chart" width="600" height="400"></canvas>

<script>
var config = new Chart(ctx, {
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

var ctx = document.getElementById('line-chart').getContext('2d');
new Chart(ctx, config);


</script>
```

</p>
</details>

## DEMO

<canvas id="line-chart" width="600" height="400"></canvas>

<script>
var config = new Chart(ctx, {
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

var ctx = document.getElementById('line-chart').getContext('2d');
new Chart(ctx, config);

</script>