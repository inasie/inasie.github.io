---
title: Jekyll 블로그 - line chart 그리기
date: 2018-11-24
last_modified_at: 2018-11-24
categories:
- IT일반
tags:
- jekyll
- 라인차트
- linechart
- chart.js
---

Jekyll 블로그에서 [chart.js](https://www.chartjs.org/)를 이용해 line chart를 그리는 예제입니다.

## chart.js import

chart.js 를 사용하기 위해 _config.yml 에 아래 라인을 추가해줍니다.

```yaml
head_scripts:
  - https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.7.2/Chart.min.js
```

## 라인 차트 그리기

아래와 같이 canvas를 하나 만들고 script 코드로 차트를 그립니다. <br>
line chart에 대한 자세한 옵션은 [여기](https://www.chartjs.org/docs/latest/charts/line.html)서 참고할 수 있습니다.

샘플코드는 [여기](https://www.chartjs.org/samples/latest/charts/line/basic.html)를 참고하여 만들었습니다.


```html
<div style="width:100%;">
  <canvas id="canvas"></canvas>
</div>

<script>
new Chart(document.getElementById("canvas"), {
    type: 'line',
    data: {
        labels: ['1', '2', '3', '4', '5', '6', '7'],
        datasets: [{
            label: '테스트 데이터셋',
            data: [
                10,
                3,
                30,
                23,
                10,
                5,
                50
            ],
            borderColor: "rgba(255, 201, 14, 1)",
            backgroundColor: "rgba(255, 201, 14, 0.5)",
            fill: true,
            lineTension: 0
        }]
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
                ticks: {
                    suggestedMin: 0,
                },
                scaleLabel: {
                    display: true,
                    labelString: 'y축'
                }
            }]
        }
    }
});

</script>
```

## 결과

<div style="width:100%;">
  <canvas id="canvas" height="300"></canvas>
</div>

<script>
new Chart(document.getElementById("canvas"), {
    type: 'line',
    data: {
        labels: ['1', '2', '3', '4', '5', '6', '7'],
        datasets: [{
            label: '테스트 데이터셋',
            data: [
                10,
                3,
                30,
                23,
                10,
                5,
                50
            ],
            borderColor: "rgba(255, 201, 14, 1)",
            backgroundColor: "rgba(255, 201, 14, 0.5)",
            fill: false,
            lineTension: 0
        },{
            label: '데이터셋2',
            pointRadius: 1,
            data: [
                3,
                10,
                10,
                13,
                30,
                2,
                30
            ],
            borderColor: "rgba(0, 141, 185, 1)",
            backgroundColor: "rgba(0, 141, 185, 0.5)",
            fill: false,
            lineTension: 0
        }]
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
                ticks: {
                    suggestedMin: 0,
                },
                scaleLabel: {
                    display: true,
                    labelString: 'y축'
                }
            }]
        }
    }
});

</script>

