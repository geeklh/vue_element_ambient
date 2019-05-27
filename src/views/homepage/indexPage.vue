<template>
  <el-row class="container">
    <el-col :span="24" class="main">首页数据显示区域</el-col>
  </el-row>
</template>

<style scoped lang="scss">
@import "~scss_vars";
.container {
  position: absolute;
  top: 0px;
  bottom: 0px;
  width: 100%;
  .main {
    display: flex;
    // background: #324057;
    position: absolute;
    top: 60px;
    bottom: 0px;
    overflow: hidden;
  }
}
</style>