<template>
  <div class="app-container">
    <div class="left">
      <LeftMain></LeftMain>
    </div>
    <div class="right">
      <RightMain></RightMain>
    </div>
  </div>
</template>

<script>
import { RightMain, LeftMain } from './view/components/index'
export default {
  name: 'App',
  components: { RightMain, LeftMain }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>

<style lang="less" scoped>
.app-container {
  display: flex;

  height: 100vh;
  width: 100vw;
  // height: 100%;
  // width: 100%;

  background-color: #282828;

  .left {
    flex: 1 1 25%;
    height: 100%;
    width: 100%;
    // flex: 1;
  }
  .right {
    flex: 1 1 75%;
    // flex: 3;
  }
}
</style>
