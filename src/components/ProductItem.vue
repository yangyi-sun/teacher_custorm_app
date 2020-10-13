<template>
  <!-- emit 发射，将组件上接受到的click事件发射给发组件中的click事件 -->
  <div class="product_item" @click="$emit('click')">
    <van-row>
      <van-col :span="4">
        <img v-if="data.photo" :src="data.photo" alt="">
        <img v-else src="../assets/sss.jpg" alt="">
      </van-col>
      <van-col :offset="1" :span="19">
        <div> <strong>名称：</strong> {{data.name}}</div>
        <div> <strong>价格：</strong> {{data.price}}</div>
        <div> <strong>描述：</strong> {{data.description}}</div>
      </van-col>
    </van-row>
  </div>
</template>
<script>
export default {
  props:['data'],
  data(){
    return {
      value:0
    }
  },
  methods:{
   
  }
}
</script>
<style scoped>
.product_item {
  margin:.5em 1em;
  padding: .5em;
  border-radius: 5px;
  height: 80px;
  border: 1px dotted #ccc;
}
.product_item img {
  width: 100%;
  border-radius: 3px;
}
</style>