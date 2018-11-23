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
new Chart(document.getElementById("canvas"), {
    type: 'line',
    data: {
        labels: ['1', '2', '3', '4', '5', '6', '7'],
        datasets: [{
            label: '테스트 데이터셋',
            data: [
                10,
                20,
                30,
                40,
                10,
                5,
                15
            ],
            borderColor: "rgba(255, 201, 14, 0.5)",
            backgroundColor: "rgba(255, 201, 14, 1)",
            fill: false,
        }
    },
    options: {
        responsive: true,
        title: {
            display: true,
            text: '라인 차트 테스트'
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
                    labelString: 'x축'
                }
            }],
            yAxes: [{
                display: true,
                scaleLabel: {
                    display: true,
                    labelString: 'y축'
                }
            }]
        }
    }
});

</script>