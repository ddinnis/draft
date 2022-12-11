<template>
  <div class="container">
    <graphItem></graphItem>
    <graphItem></graphItem>
    <graphItem></graphItem>
    <graphItem></graphItem>
    <graphItem></graphItem>
  </div>
</template>

<script>
import graphItem from '@/components/graph-item'
export default {
  name: 'LeftMain',
  components: { graphItem }
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
