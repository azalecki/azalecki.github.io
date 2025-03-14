---
layout: page
title: test
description: 
img: assets/img/thumbnails/sanjuan_crop.png
importance: 1
category: research
---

```echarts
{
  "title": {
    "text": "ECharts Getting Started Example"
  },
  "responsive": true,
  "tooltip": {},
  "legend": {
    "top": "30px",
    "data": ["sales"]
  },
  "xAxis": {
    "data": ["Shirts", "Cardigans", "Chiffons", "Pants", "Heels", "Socks"]
  },
  "yAxis": {},
  "series": [
    {
      "name": "sales",
      "type": "bar",
      "data": [5, 20, 36, 10, 10, 20]
    }
  ]
}
```

```echarts

var chart = echarts.init(document.getElementById('main'));

var option = {
  tooltip: {
    trigger: 'axis',
    axisPointer: {
      type: 'shadow'
    }
  },
  grid: {
    left: '3%',
    right: '4%',
    bottom: '3%',
    containLabel: true
  },
  xAxis: {
    type: 'value',
    boundaryGap: [0, 0.1]
  },
  yAxis: {
    type: 'category',
    data: ['NonEnglish Materials', 'InPerson Homework Help', 'CyberNavigators', 'Citizenship Corner', 'Mental Health Services', 'Hotspot Lending', 'Chromebook Lending', 'YouMedia', 'Meeting Room', 'Study Rooms']
  },
  series: [
    {
      name: 'Yes',
      type: 'bar',
      data: [1, 0, 1, 1, 1, 0, 1, 0, 1, 1], // Counts for "Yes"
      itemStyle: {
        color: '#ffae49'
      }
    },
    {
      name: 'No',
      type: 'bar',
      data: [0, 1, 0, 0, 0, 1, 0, 1, 0, 0], // Counts for "No"
      itemStyle: {
        color: '#44a5c2'
      }
    }
  ]
};

chart.setOption(option);

```

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>ECharts</title>
    <!-- Include the ECharts file you just downloaded -->
    <script src="echarts.js"></script>
  </head>
  <body>
    <!-- Prepare a DOM with a defined width and height for ECharts -->
    <div id="main" style="width: 600px;height:400px;"></div>
    <script type="text/javascript">
      // Initialize the echarts instance based on the prepared dom
      var myChart = echarts.init(document.getElementById('main'));

      // Specify the configuration items and data for the chart
      var option = {
        title: {
          text: 'ECharts Getting Started Example'
        },
        tooltip: {},
        legend: {
          data: ['sales']
        },
        xAxis: {
          data: ['Shirts', 'Cardigans', 'Chiffons', 'Pants', 'Heels', 'Socks']
        },
        yAxis: {},
        series: [
          {
            name: 'sales',
            type: 'bar',
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      };

      // Display the chart using the configuration items and data just specified.
      myChart.setOption(option);
    </script>
  </body>
</html>