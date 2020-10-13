<template>
  <div class="order">
    <van-nav-bar title="我的订单" />
    <van-tabs v-model="active" color="#1659a0" @click="tabClickHandler">
      <van-tab title="全部"></van-tab>
      <van-tab title="待派单"> </van-tab>
      <van-tab title="待接单"></van-tab> 
      <van-tab title="待服务"></van-tab>
      <van-tab title="待确认"></van-tab>
      <van-tab title="已完成"></van-tab>
    </van-tabs>
    <!-- 订单 -->
    <div>
      <briup-order-item 
        v-for="o in orders" 
        :key="o.id" 
        :data="o">
      </briup-order-item>
    </div>      


  </div>
</template>
<script>
import { mapState } from 'vuex'
import {get} from '../../http/axios'
export default {
  data(){
    return {
      active:0,
      orders:[],
      status:null
    }
  },
  computed:{
    ...mapState("user",["info"])
  },
  created(){
    this.loadOrders();
  },
  methods:{
    // 加载我的订单
    loadOrders(){
      let url = "/order/query";
      let params = {
        customerId:this.info.id,
        status:this.status
      }
      get(url,params).then((response)=>{
        this.orders = response.data;
      })
    },
    tabClickHandler(name,title){
      //修改当前staus的值，重新加载
      this.status=title ==="全部" ? null :title;
      this.loadOrders();
    }
  }
}
</script>
<style scoped>
.order {
  background: #f1f1f1;
}
</style>