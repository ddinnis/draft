<template>
  <div class="option-item">
    <div class="label">{{ title }}：</div>
    <el-select
      class="select"
      v-model="value"
      placeholder="请选择"
      size="mini
  "
      @change="selectClick"
    >
      <el-option
        v-for="item in options"
        :key="item"
        :label="item"
        :value="item"
      ></el-option>
    </el-select>
  </div>
</template>

<script>
export default {
  name: 'OptionItem',
  props: {
    options: {
      type: Array,
      default() {
        return [1]
      }
    },
    title: {
      type: String,
      default: '经度选择'
    }
  },
  data() {
    return { value: '', res: [] }
  },
  methods: {
    selectClick(item) {
      console.log('item', item)
    }
  }
}
</script>

<style lang="less" scoped>
.option-item {
  display: flex;
  justify-content: flex-start;
  align-items: center;

  padding: 2.5% 1%;
  .label {
    color: aliceblue;
    flex: 2;
  }
  .select {
    flex: 3;
  }
}
</style>
