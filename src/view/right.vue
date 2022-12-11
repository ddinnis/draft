<template>
  <div class="container">
    <TopItem></TopItem>
    <el-divider></el-divider>
    <div class="main">
      <div class="middle">
        <MiddlePart></MiddlePart>
      </div>
      <el-divider></el-divider>
      <div class="bottom">
        <div class="bottom-left">
          <h4 class="text sub-title">区域同化</h4>
          <div class="option-items">
            <OptionItem
              :options="longitudeOptions"
              title="经度选择"
            ></OptionItem>
            <OptionItem
              :options="latitudeOptions"
              title="纬度选择"
            ></OptionItem>
            <OptionItem
              :options="horizontalResolution"
              title="水平分辨率"
            ></OptionItem>
            <OptionItem
              :options="highResolution"
              title="高度分辨率"
            ></OptionItem>
          </div>
          <div class="btn-operation">
            <el-button size="small" class="btn">开始同化</el-button>
            <div class="btn-result">
              <span class="text">响应时间：</span>
              <span class="text">模型精度：</span>
            </div>
          </div>
        </div>
        <div class="bottom-right">
          <OptionItem
            :options="hightOptions"
            title="高度选择"
            class="option-item"
          ></OptionItem>
          <div class="item-container">
            <GraphItem></GraphItem>
            <GraphItem></GraphItem>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TopItem from './components/top-item'
import OptionItem from './components/option-item'
import GraphItem from '../components/graph-item'

import MiddlePart from './components/middle-part.vue'
export default {
  name: 'RightMain',
  components: { TopItem, OptionItem, GraphItem, MiddlePart },
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
.container {
  height: 100%;

  .main {
    display: flex;
    flex-direction: column;
    .middle {
      // flex: 1;
      height: 38%;
    }
    .bottom {
      // flex: 1;
      height: 38%;
    }
  }

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

  .bottom {
    display: flex;

    .bottom-left {
      flex: 1;
      padding: 0 1.5%;

      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .bottom-right {
      flex: 2;
      display: flex;
      .item-container {
        height: 100%;
      }
      .item {
        flex: 1;
      }
    }
  }
  .bottom .bottom-right {
    flex-direction: column;
    .option-item {
      padding-top: 0;
      width: 50%;
      margin-left: 47%;
    }
    .item-container {
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

  .el-divider {
    background-color: #254b8d;
  }
  .el-divider--horizontal {
    margin: 2.4% 0;
  }
}

// el-date-picker
</style>
