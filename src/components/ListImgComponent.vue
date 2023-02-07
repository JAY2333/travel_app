<template>
  <div id="box">
    <ul>
      <li v-for="v in list" :key="v.value">
        <img @click="push" v-bind:src="v.src" alt="" />
        <h4>{{ v.des }}</h4>
        <div>
          <span>票价:</span>
          <span style="color: brown;">{{ v.price }}</span>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ListImgComponent',
  data () {
    return {
      list: [
        {
          value: '0',
          src: require('../assets/Picture/tieshan.jpg'),
          des: '铁山',
          price: 200
        },
        {
          value: '1',
          src: require('../assets/Picture/tieshan.jpg'),
          des: '测视图',
          price: 198
        },
        {
          value: '2',
          src: require('../assets/Picture/tieshan.jpg'),
          des: '测视图',
          price: 198
        },
        {
          value: '3',
          src: require('../assets/Picture/tieshan.jpg'),
          des: '测视图',
          price: 198
        },
        {
          value: '3',
          src: require('../assets/Picture/tieshan.jpg'),
          des: '测视图',
          price: 198
        },
        {
          value: '3',
          src: require('../assets/Picture/tieshan.jpg'),
          des: '测视图',
          price: 198
        }
      ]
    }
  },
  methods: {
    push () {
      console.log(5555)
    }
  }
}
</script>

<style scoped>
#box ul{
  display: flex;
  flex-wrap: wrap;
}
#box li{
  padding: 3px;
  list-style: none;
  margin-right: 15px;
  border: 1px outset rgb(177, 169, 169);
  margin-top: 10px;
}
#box li > h4{
  text-align:center;
  height: 20px;
  font-size: 20px;
  line-height: 20px;
}
#box img{
  width: 400px;
  height: 300px;
  cursor: pointer;
}
#box li > div{
  text-align: right;
  margin-right: 5px;
}
</style>
