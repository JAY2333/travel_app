<template>
  <div class="header_view">
    <el-page-header @back="goBack" content="详情页面"></el-page-header>
    <select-input/>
      <div class="block">
      <el-image
        style="width: 30px; height: 30px;border-radius:50%;margin:10px;float: left; "
        :src="url"
      ></el-image>
      <div class="login">
        <el-link type="danger" >登录</el-link>
        <span>/</span>
        <el-link type="info">注册</el-link>
      </div>
    </div>
  </div>
</template>

<script>
import SelectInput from '../components/SelectInput.vue'
export default {
  name: 'HeaderView',
  components: {
    SelectInput
  },
  data () {
    return {
      url: 'https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg'
    }
  },
  methods: {
    goBack () {
      console.log('go back')
    }
  }
}
</script>

<style scoped>
.header_view{
  height: 60px;
  width: 100%;
}
.el-page-header{
    line-height: 60px;
    width: 20%;
    height: 100%;
    float: left;
    clear: both;
    overflow: hidden;
}
.block{
  overflow: hidden;
}
.login{
  font-size: large;
  color: #c23ac2;
}
.el-link{
  font-size: large;
  color: #c23ac2;
  clear: both;
}
</style>
