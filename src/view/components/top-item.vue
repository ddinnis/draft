<template>
  <div class="top">
    <h2>云南地区高精度区域风场同化模型软件</h2>
    <div class="top-sub">
      <div class="top-sub-left">
        <span class="label">同化时间输入：</span>
        <el-date-picker
          v-model="value1"
          type="datetime"
          placeholder="选择日期时间"
          change
          @input="changeTime"
          size="small"
        ></el-date-picker>
      </div>
      <div class="top-sub-right">
        <span class="label">文件检索：</span>
        <el-autocomplete
          size="small"
          class="inline-input"
          v-model="state1"
          :fetch-suggestions="querySearch"
          placeholder="文件检索"
          @select="handleSelect"
        ></el-autocomplete>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopItem',
  data() {
    return {
      value1: '',
      state1: ''
    }
  },
  methods: {
    changeTime(val) {
      console.log(val)
    },
    querySearch(queryString, cb) {
      console.log('queryString', queryString)
      const res = [
        { value: '三全鲜食（北新泾店）', address: '长宁区新渔路144号' },
        {
          value: 'Hot honey 首尔炸鸡（仙霞路）',
          address: '上海市长宁区淞虹路661号'
        }
      ]
      cb(res)
    },
    handleSelect(item) {
      console.log(item)
    }
  }
}
</script>

<style lang="less" scoped>
.top {
  h2 {
    padding-top: 0.5%;
    text-align: center;
    color: aliceblue;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
  }
  .top-sub {
    display: flex;
    justify-content: space-between;
    margin: 1.5% 2% 0;
  }
  .label {
    color: aliceblue;
  }
}
</style>
