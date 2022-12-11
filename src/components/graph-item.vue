<template>
  <div class="graph-item">
    <div id="myChart"></div>
  </div>
</template>

<script>
import * as echarts from 'echarts'
export default {
  name: 'GraphItem',
  data() {
    return {}
  },
  mounted() {
    var myChart = echarts.init(document.getElementById('myChart'))
    var option = {
      xAxis: {
        type: 'category',
        data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
      },
      yAxis: {
        type: 'value'
      },
      series: [
        {
          data: [820, 932, 901, 934, 1290, 1330, 1320],
          type: 'line',
          smooth: true
        }
      ]
    }
    myChart.setOption(option)
  }
}
</script>

<style lang="less" scoped>
.graph-item {
  border: 1px solid #254b8d;
  width: 100%;
  height: 100%;
}
</style>
