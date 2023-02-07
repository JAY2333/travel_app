<template>
  <div style="width :100%;height:100%">
    <el-row class="tac" style="width :100%;height:92%">
      <el-col :span="12">
        <el-menu
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose"
          text-color="#289F90"
        >
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>首页</span>
            </template>
            <el-menu-item-group >
              <template slot="title">心仪之地</template>
              <el-menu-item index="1-1">强力推荐</el-menu-item>
              <el-menu-item index="1-2">个性推荐</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="周围逛逛">
              <el-menu-item index="1-3">本地景点</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">更多</template>
              <el-menu-item index="1-4-1">外省景点</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span slot="title">我的足迹</span>
          </el-menu-item>
          <el-menu-item index="3" disabled>
            <i class="el-icon-document"></i>
            <span slot="title">关注过</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">个人中心</span>
          </el-menu-item>
        </el-menu>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'LeftHomeView',
  methods: {
    handleOpen (key, keyPath) {
      console.log(key, keyPath)
    },
    handleClose (key, keyPath) {
      console.log(key, keyPath)
    }
  }
}
</script>

<style scoped>
.el-col{
  width: 100%;
  height: 100%;
}
.el-menu{
  margin-top: 60px;
  width: 99%;
  color: none;
  height: 100%;
  background-color: #CCCCFF;
}
</style>
