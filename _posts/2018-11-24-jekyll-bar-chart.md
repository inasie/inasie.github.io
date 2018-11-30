---
title: Jekyll 블로그 - bar chart 그리기
date: 2018-11-24
last_modified_at: 2018-11-24
categories:
- IT일반
tags:
- jekyll
- 막대차트
- bar chart
- chart.js
---

Jekyll 블로그에서 [chart.js](https://www.chartjs.org/)를 이용해 bar chart를 그리는 예제입니다.

## chart.js import

chart.js 를 사용하기 위해 _config.yml 에 아래 라인을 추가해줍니다.

```yaml
head_scripts:
  - https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.7.2/Chart.min.js
```

## 막대 차트 그리기

아래와 같이 canvas를 하나 만들고 script 코드로 차트를 그립니다. <br>
line chart에 대한 자세한 옵션은 [여기](https://www.chartjs.org/docs/latest/charts/bar.html)서 참고할 수 있습니다.

샘플코드는 [여기](https://www.chartjs.org/samples/latest/charts/bar/vertical.html)를 참고하여 만들었습니다.


```html
<div style="width:100%;">
<canvas id="canvas" height="300"></canvas>
</div>

<script>

new Chart(document.getElementById("canvas"), {
    type: 'bar',
    data: {
        labels: ['가가가가가가가가가가가가가가', '나나나나나나', '다다다다다다', '라라라라라라', '마마마', '바바바바바바바', '사사사사사사사사', '아아아아아아', '자자자자', '차차차차차차차', '카카카카카카카'],
        datasets: [{
            label: '테스트 데이터셋',
            data: [
                10,
                3,
                30,
                23,
                10,
                5,
                15,
                20,
                13,
                5,
                9
            ],
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
            callbacks: {
                title: function(tooltipItems, data) {
                    return data.labels[tooltipItems[0].datasetIndex];
                }
            }
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
                ticks: {
                    autoSkip: false
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

</script>
```

## 결과

<div style="width:100%;">
<canvas id="canvas" height="300"></canvas>
</div>

<script>

new Chart(document.getElementById("canvas"), {
    type: 'bar',
    data: {
        labels: ['가가가가가가가가가가가가가가', '나나나나나나', '다다다다다다', '라라라라라라', '마마마', '바바바바바바바', '사사사사사사사사', '아아아아아아', '자자자자', '차차차차차차차', '카카카카카카카'],
        datasets: [{
            label: '테스트 데이터셋',
            data: [
                10,
                3,
                30,
                23,
                10,
                5,
                15,
                20,
                13,
                5,
                9
            ],
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
            callbacks: {
                title: function(tooltipItems, data) {
                    return data.labels[tooltipItems[0].datasetIndex];
                }
            }
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
                ticks: {
                    autoSkip: false,
                    callback: function(value, index, values) {
                        if (value.length > 8)
                          return value.substr(0, 5) + "...";
                        else
                          return value;
                    }
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
