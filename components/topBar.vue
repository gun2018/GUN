<style>
.header {
  width: 100%;
  height: 60px;
  padding: 10px;
  line-height: 40px;
  border-bottom: 1px solid #DCDFE6;
  font-size: 16px;
  position: fixed;
  top: 0;
  background-color: #fff;
}
.logo {
  float: left;

}
.status {
  float: right;
}
.nickname {
  margin: 0 10px;
  float: right;
}
.search-input {
  display: inline-block;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 170px;
  height: 30px;
}
.search-input input {
  width: 170px;
  height: 30px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  height: 30px;
  padding: 0 5px 0 25px;
  border-radius: 15px;
  border: 1px solid #DCDFE6;
}
.search-input i {
   color: #909399;
}
.search-input i {
  position: absolute;
  z-index: 1;
  line-height: 30px;
  left: 5px;
}
</style>

<template>
  <div>
    <div class="header">
      <div class="logo">GUN</div>
      <div class="search-input">
        <i class="iconfont icon-search"></i>
        <input type="" name="" placeholder="搜索">
      </div>
      <div>
        <div v-if="userData">
          <span class="nickname">{{userData.nickname}}</span>
          <a @click="signout" href="javascript:void(0);" class="status">登出</a>
        </div>
        <div v-else>
          <nuxt-link to="/sign/in">登录</nuxt-link>
          <nuxt-link to="/sign/up">注册</nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>
<script type="text/javascript">
import { mapState } from 'vuex';
export default {
  methods: {  
    async signout() {
      const { data } = await this.$get('/signout')

      if (data.msg.success) {
        this.$store.commit('setUserData', null);
      }
    }
  },
  computed: {
    ...mapState(['userData'])
  }
}
</script>
