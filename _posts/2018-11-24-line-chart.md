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

updated #3

<canvas id="canvas" width="800" height="600"></canvas>

<script>
var MONTHS = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];
new Chart(document.getElementById("canvas"), {
    type: 'line',
    data: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [{
            label: '테스트 데이터셋1',
            data: [
                10,
                20,
                30,
                40,
                10,
                5,
                15
            ],
            borderColor: "rgba(150, 175, 200, 0.2)",
            backgroundColor: "rgba(150, 175, 200, 1)",
            fill: false,
        }, {
            label: '테스트 데이터셋2',
            fill: false,
            data: [
                40,
                10,
                50,
                60,
                10,
                35,
                72
            ],
            borderColor: "rgba(16, 240, 138, 0.2)",
            backgroundColor: "rgba(16, 240, 138, 1)",
        }]
    },
    options: {
        responsive: true,
        title: {
            display: true,
            text: 'Chart.js Line Chart'
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