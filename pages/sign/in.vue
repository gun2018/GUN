<template>
  <div>
    <h4 class="title">
        <div class="normal-title">
            <nuxt-link to="/sign/in" class="active">登陆</nuxt-link>
            <b>·</b>
            <nuxt-link to="/sign/up">注册</nuxt-link>
        </div>
    </h4>
    <form class="sign-in-container">
        <div class="input-sign">
            <input type="" name="" placeholder="邮箱">
        </div>
        <div class="input-sign input-especially">
            <input type="" name="" placeholder="密码">
        </div>
        <div class="remember-button">
            <input type="checkbox" name="session[remember_me]" value="true" checked="checked" class="remember-check">
            <span class="remember-text">记住我</span>
        </div>
          <nuxt-link to="" class="problem-link">登陆遇到问题？</nuxt-link>
        <div class="sign-button sign-in">登陆</div>
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
      email: ''
    }
  },
  methods: {
    async signin() {
      const { data } = await this.$post('/signin', {
        nickname: this.nickname,
        email: this.email,
        password: this.password
      })

      if (data.msg.success) {
        this.$store.commit('setUserData', data.userData);
      }
    }
  }
};
</script>