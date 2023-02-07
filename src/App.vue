<template>
  <div id="app">
    <el-container style="height: 100%">
      <el-aside width="200px"><left-home-view /></el-aside>
      <el-container>
        <el-header><header-view /></el-header>
        <el-main>
          <!-- <vue-particles
            class="main-bg"
            color="#f4f4f4"
            :particleOpacity="0.7"
            :particlesNumber="100"
            shapeType="circle"
            :particleSize="4"
            linesColor="#f4f4f4"
            :linesWidth="1"
            :lineLinked="true"
            :lineOpacity="0.4"
            :linesDistance="150"
            :moveSpeed="3"
            :hoverEffect="true"
            hoverMode="grab"
            :clickEffect="true"
            clickMode="push"
          /> -->
          <!-- <img-component /> -->
          <!-- <list-img-component /> -->
          <user-manger-component />
          <router-view></router-view>
        </el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </el-container>
  </div>
</template>
<script>
import LeftHomeView from './views/LeftHomeView.vue'
import HeaderView from './views/HeaderView.vue'
import UserMangerComponent from './components/UserMangerComponent.vue'

export default {
  name: 'app',
  components: { LeftHomeView, HeaderView, UserMangerComponent },
  created () {
    setTimeout(() => {
      window.L2Dwidget.init({
        pluginRootPath: 'static/live2dw/',
        pluginJsPath: 'lib/',
        pluginModelPath: 'live2d-widget-model-haru_2/assets/',
        tagMode: false,
        debug: false,
        model: {
          jsonPath:
            'static/live2dw/live2d-widget-model-haru_2/assets/haru02.model.json'
        },
        display: { position: 'right', width: 200, height: 350 },
        mobile: { show: true },
        log: false
      })
    }, 1000)
  }
}
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
}

.el-header,
.el-footer {
  background-color: #b3c0d1;
  color: #333;
  line-height: 60px;
  height: 80px;
}

.el-aside {
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
}
/* #e9eef3 */
.el-main {
  background-color:#e9eef3;
  color: #333;
  line-height: 60px;
}

  /* .main-bg{
    position:absolute;
    width:auto;
    height: 600px;
    z-index: 1;
    top: 0;
  } */

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>
