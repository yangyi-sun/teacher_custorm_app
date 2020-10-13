<template>
<div>
    <briup-fulllayout title="帮助及问题反馈">
    <van-divider>常见问题</van-divider>
    <van-collapse v-model="activeNames">
  <van-collapse-item title="优惠券如何使用" name="1">下单时自动选择最优方式</van-collapse-item>
  <van-collapse-item title="取消订单后钱什么时候到账" name="2">取消订单后钱在两个小时内到账</van-collapse-item>
  <van-collapse-item title="可以固定一个家教进行服务吗" name="3" >可以指定老师进行服务</van-collapse-item>
  <van-collapse-item title="如何选择上一次服务的老师" name="4" >点击已完成的订单进行再次下单</van-collapse-item>
  <van-collapse-item title="预约成功之后在哪里查看" name="5" >在我的订单中可以进行查看</van-collapse-item>
  </van-collapse>

    <van-divider>更多问题</van-divider>
    <van-grid column-num="3"  square>
  <van-grid-item  text="订单相关" />
  <van-grid-item  text="客户端使用" />
  <van-grid-item  text="优惠券与活动" />
  <van-grid-item  text="支付与费用" />
  <van-grid-item  text="服务相关" />
  </van-grid>
  </briup-fulllayout>
</div>
</template>
<script>
export default {
    data() {
    return {
      activeNames: ['1']
    };
  }
}
</script>