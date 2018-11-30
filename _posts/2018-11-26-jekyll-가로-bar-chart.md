---
title: Jekyll 블로그 - 가로 bar chart 그리기
date: 2018-11-26
last_modified_at: 2018-11-26
categories:
- IT일반
tags:
- jekyll
- 막대차트
- bar chart
- chart.js
---

Jekyll 블로그에서 [chart.js](https://www.chartjs.org/)를 이용해 가로 bar chart를 그리는 예제입니다.

## chart.js import

chart.js 를 사용하기 위해 _config.yml 에 아래 라인을 추가해줍니다.

```yaml
head_scripts:
  - https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.7.2/Chart.min.js
```

## 막대 차트 그리기

아래와 같이 canvas를 하나 만들고 script 코드로 차트를 그립니다. <br>
bar chart에 대한 자세한 옵션은 [여기](https://www.chartjs.org/docs/latest/charts/bar.html)서 참고할 수 있습니다.

샘플코드는 [여기](https://www.chartjs.org/samples/latest/charts/bar/vertical.html)를 참고하여 만들었습니다.

<details><summary>코드 접기/펴기</summary>

<div markdown="1">

```html
<div style="width:100%;">
<canvas id="canvas" height="300"></canvas>
</div>

<script>

new Chart(document.getElementById("canvas"), {
    type: 'horizontalBar',
    data: {
        labels: ['가', '나', '다', '라', '마', '바', '사', '아', '자', '차', '카', '타', '파', '하'],
        datasets: [{
            label: '테스트 데이터셋',
            data: [10, 3, 30, 23, 10, 5, 15, 25, 2, 4, 1, 13, 52, 23],
            borderColor: "rgba(255, 201, 14, 1)",
            backgroundColor: "rgba(255, 201, 14, 0.5)",
            fill: false,
        }]
    },
    options: {
        responsive: true,
        title: {
            display: true,
            text: '막대 차트 테스트'
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
                },
            }],
            yAxes: [{
                display: true,
                ticks: {
                    autoSkip: false,
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
</div>
</details>

## 결과

<div style="width:100%;">
<canvas id="canvas" height="300"></canvas>
</div>

<script>

new Chart(document.getElementById("canvas"), {
    type: 'horizontalBar',
    data: {
        labels: ['가', '나', '다', '라', '마', '바', '사', '아', '자', '차', '카', '타', '파', '하'],
        datasets: [{
            label: '테스트 데이터셋',
            data: [10, 3, 30, 23, 10, 5, 15, 25, 2, 4, 1, 13, 52, 23],
            borderColor: "rgba(255, 201, 14, 1)",
            backgroundColor: "rgba(255, 201, 14, 0.5)",
            fill: false,
        }]
    },
    options: {
        responsive: true,
        title: {
            display: true,
            text: '막대 차트 테스트'
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
                },
            }],
            yAxes: [{
                display: true,
                ticks: {
                    autoSkip: false,
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
