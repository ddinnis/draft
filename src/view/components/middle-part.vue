<template>
  <div class="middle-part">
    <div class="middle-left">
      <h4 class="text sub-title">单点同化</h4>
      <div class="option-items">
        <OptionItem :options="longitudeOptions" title="经度选择"></OptionItem>
        <OptionItem :options="latitudeOptions" title="纬度选择"></OptionItem>
        <OptionItem :options="hightOptions" title="高度选择"></OptionItem>
        <OptionItem
          :options="horizontalResolution"
          title="水平分辨率"
        ></OptionItem>
        <OptionItem :options="highResolution" title="高度分辨率"></OptionItem>
      </div>
      <div class="btn-operation">
        <el-button size="small" class="btn">开始同化</el-button>
        <div class="btn-result">
          <span class="text">响应时间：</span>
          <span class="text">模型精度：</span>
        </div>
      </div>
    </div>
    <div class="middle-right">
      <div class="item">
        <GraphItem></GraphItem>
      </div>
      <div class="item">
        <GraphItem></GraphItem>
      </div>
    </div>
  </div>
</template>

<script>
import GraphItem from '../../components/graph-item'
import OptionItem from './option-item'

export default {
  name: 'MiddlePart',
  components: { GraphItem, OptionItem },
  data() {
    return {
      longitudeOptions: [100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110],
      latitudeOptions: [20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30],
      hightOptions: [80, 90, 100],
      horizontalResolution: ['1°'],
      highResolution: ['2KM']
    }
  }
}
</script>

<style lang="less" scoped>
.text,
.label {
  color: aliceblue;
}
.sub-title {
  font-family: 'Noto Sans SC';
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 16px;
}
.middle-part {
  display: flex;
  flex: 40%;

  .middle-left {
    flex: 1;
    padding: 0 1.5%;
  }
  .middle-right {
    flex: 2;
    display: flex;

    .item {
      flex: 1;
    }
  }
}
.btn-operation {
  display: flex;
  flex-direction: column;
  .btn {
    margin: 3% 20%;
    color: #fff;
    background-color: #0a66d8;
    border: 1px solid #0a66d8;
    /* Shadow/default */

    box-shadow: 0px 1px 1px rgba(0, 0, 0, 0.12),
      0px 2px 5px rgba(59, 59, 59, 0.08);
  }
  .btn-result {
    display: flex;
    justify-content: space-between;
  }
}
</style>
