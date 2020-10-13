<template>
  <div class="user">
    <div class="header">
      <div class="photo">
        <img src="../../assets/sss.jpg" alt=""/>
      </div>
      <div class="name">{{info.name}}</div>
    </div>
    <van-cell-group>
    <van-cell title="常用地址" is-link to="/manager/address" />
    <van-cell title="所有订单" is-link to="/manager/Order" />
    <van-cell title="帮助及问题反馈" is-link to="/manager/Help" />
    <van-cell is-link @click="showPopup">联系我们</van-cell>

      <van-popup v-model="show">联系电话：6082333</van-popup>

    </van-cell-group>
    <div class="btn" type="primary" @click="logoutHandler">
      退出
    </div>
  </div>
</template>
<script>
import {mapState, mapActions} from 'vuex'
export default {
  data() {
    return {
      show: false
    }
  },
  methods:{
    
  showPopup(){
      this.show = true;
  },
    ...mapActions('user',['logout']),
    toAddressHandler(){
      // this.$router.push({path:'/manager/address'})
    },
    logoutHandler(){
      this.logout()
      .then(()=>{
        this.$router.push({path:'/login'})
      })
    }
  },
  computed:{
    ...mapState("user",["info"])
  }
}
</script>

<style scoped>
.header {
  padding-top: 46px;
  text-align: center;
  background: #ece358;
  margin-bottom: 2em;
}

.header .photo {
  margin: 0 auto;
  width: 10em;
  height: 10em;
  border-radius: 50%;
  box-sizing: border-box;
  border:1px solid #1659a0;
  overflow:hidden;
  padding: 1em;
}
.header .name {
  line-height: 3em;
  font-size: 16px;
  color: #ffffff;

}
.header .photo img {
 width: 100%;
 border-radius: 50%;
}

.btn {
  width: 90%;
  margin: 1em auto;
  line-height: 3em;
  text-align: center;
  border: 1px solid #ededed;
  border-radius: 1.5em;
}

</style>