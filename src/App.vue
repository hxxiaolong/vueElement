<template>
  <div id="app">
    <el-row>
      <el-col :span="24">
        <div class="grid-content bg-purple-dark title"></div>
      </el-col>
    </el-row>
    <el-row :gutter="30" class="bottom_main">
      <el-col :span="4" class="list-menu-wrap" style="padding-right: 0px">
        <el-menu default-active="2" class="el-menu-vertical-demo persent100" style="padding-right: 0px" @open="handleOpen" @close="handleClose">
          <el-submenu index="1" class="persent100">
            <template slot="title"><i class="el-icon-message"></i>导航一</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2"><i class="el-icon-menu"></i>导航二</el-menu-item>
          <el-menu-item index="3"><i class="el-icon-setting"></i>导航三</el-menu-item>
        </el-menu>
      </el-col>
      <el-col :span="20">
        <router-view></router-view>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  export default {
    name: 'app',
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  };
</script>

<style scope lang="scss" rel="stylesheet/scss">
  @import "common/css/normal";

  .title {
    height: 100px;
  }

  .el-row {
    &:last-child {
      margin-bottom: 0;
    }
  }

  .bg-purple-dark {
    background: #99a9bf;
  }

  .bg-purple {
    background: #d3dce6;
  }

  .bg-purple-light {
    background: #e5e9f2;
  }

  .grid-content {
    min-height: 36px;
  }

  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }

  .list-menu-wrap {
    height: calc(100vh - 100px);
    overflow: auto;
    background-color: #D3DCE6;
  }

  .list-menu {
    text-align: center;
    height: 34px;
    line-height: 34px;
  }

  .bottom_main {
    margin-right: 0px !important;
  }

</style>

