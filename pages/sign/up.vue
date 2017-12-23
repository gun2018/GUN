<template>
  <div>
    <h4 class="title">
        <div class="normal-title">
            <nuxt-link to="/sign/in">登陆</nuxt-link>
            <b>·</b>
            <nuxt-link to="/sign/up" class="active">注册</nuxt-link>
        </div>
    </h4>
    <form class="sign-in-container">
        <div class="input-sign">
            <input type="text" v-model="nickname" name="" placeholder="昵称">
        </div>
        <div class="input-sign">
            <input type="text" name="" v-model="email" placeholder="邮箱">
        </div>
        <div class="input-sign">
            <input type="text" name="" v-model="emailCode" placeholder="验证码">
        </div>
        <div class="input-sign input-especially">
            <input type="password"  v-model="password" name="" placeholder="密码">
        </div>
        <div class="sign-button sign-up">注册</div>
        <div class="sign-tip">点击“注册”即表示您同意接受GUN的操控 :) </div>
    </form>
  </div>
</template>
<script>


export default {
  layout: 'sign',
  data() {
    return {
      nickname: '',
      password: '',
      email: '',
      emailCode: ''
    }
  },
  methods: {  
    async signup() {
      const { data } = await this.$post('/signup', {
        nickname: this.nickname,
        email: this.email,
        emailCode: this.emailCode,
        password: this.password
      })
      if (data.msg.success) {
        this.$store.commit('setUserData', data.userData);
      }
    }
  }
};
</script>