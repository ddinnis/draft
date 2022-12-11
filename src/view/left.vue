<template>
  <div class="container">
    <graphItem :chartData="lineChartData"></graphItem>
    <graphItem :chartData="lineChartData"></graphItem>
    <graphItem :chartData="lineChartData"></graphItem>
    <graphItem :chartData="lineChartData"></graphItem>
    <graphItem :chartData="lineChartData"></graphItem>
  </div>
</template>

<script>
import graphItem from '@/components/graph-item'
export default {
  name: 'LeftMain',
  components: { graphItem },
  data() {
    return {
      lineChartData: {
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
    }
  }
}
</script>

<style lang="less" scoped>
.container {
  // border: 1px solid #254b8d;
  height: 100%;

  display: flex;
  flex-direction: column;

  graphItem {
    flex: 1;
  }
}
</style>
