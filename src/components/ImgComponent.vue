<template>
  <div>
      <h1 class="animate__animated animate__bounce"
      enter-active-class="animate__swing"
      leave-active-class="animate__slideOutDown"> 你站在桥上看风景
                                                  看风景的人在楼上看你
                                                  明月装饰了你的窗子
                                                  你装饰了别人的梦</h1>
      <el-carousel :interval="4000" type="card" height="480px" style="text-align: center; margin-top: 30px">
        <div v-if="isTrue">
          <el-carousel-item  v-for="(item,index) in url" :key="index">
              <el-image  style="height:80%"
              :src="url[index]"
            ></el-image>
            <div>{{index}}</div>
          </el-carousel-item>
        </div>
        <el-empty v-if="!isTrue" description="无数据"></el-empty>
      </el-carousel>
  </div>
</template>
<script>
import 'animate.css'
export default {
  name: 'ImgComponent',
  data () {
    return {
      url: ['https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg']
    }
  },
  computed: {
    isTrue () {
      return this.url.length > 0
    }
  }
}
</script>

<style scoped>

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}

</style>
