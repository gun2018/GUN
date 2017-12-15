
<style>
h4 {
  font-size: 18px;
}
.main {
  margin: 0 auto;
  padding: 50px;
  width: 9.661836rem;
}
.title {
  margin-bottom: 50px;
}
.sign-in-container {
  font-size: 12px;
}
.title a, .title b {
  padding: 10px;
  color: #969696;
}
.title .active {
  font-weight: 700;
  color: #ea6f5a;
  border-bottom: 2px solid #ea6f5a;
}
.normal-title {
  text-align: center;
}
form .input-sign {
  height: 1.207729rem;
  width: 100%;
}
form .input-sign input {
  padding: 4px 12px;
  height: 100%;
  width: 100%;
  background-color: #F8F8F8;
  border-top: 1px solid #c8c8c8;
  border-right: 1px solid #c8c8c8;
  border-left: 1px solid #c8c8c8;
  margin-bottom: 0;
}
form .input-especially input {
  border-bottom: 1px solid #c8c8c8;
}
.remember-button {
  float: left;
  margin: 15px 0;
  color: #969696;
}
.problem-link {
  float: right;
  margin: 15px 0;
  color: #969696;
}
.sign-button {
  width: 100%;
  clear: both;
  text-align: center;
  color: #fff;
  font-size: 18px;
  height: 1.062802rem;
  line-height: 1.062802rem;
  border-radius: 0.531401rem;
}
.sign-in {
  background: #3194d0;
}
.sign-up {
  background: #42c02e;
  margin-top: 20px;
}
.sign-tip {
  margin: 10px 0;
  text-align: center;
  color: #969696;
}

@media (min-width: 769px) {
  body {
    background-color: #F1F1F1;
    padding-top: 60px;
  }
  .sign .main {
    width: 400px;
    box-shadow: 0 0 8px rgba(0,0,0,.1);
    background-color: #fff;
  }
  .sign form .input-sign {
    height: 50px;
  }
  .sign .sign-button {
    height: 44px;
    line-height: 44px;
    border-radius: 22px;
  }
}

 @media (max-width: 769px) {
  .sign .main {
    width: 9.661836rem;
  }
  .sign form .input-sign {
    height: 1.207729rem;
  }
  .sign .sign-button {
    height: 1.062802rem;
    line-height: 1.062802rem;
    border-radius: 0.531401rem;
  }
}
</style>

<template>
  <div class="sign">
    <div class="main">
          <nuxt/>
        <div>

        </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex';

export default {
  async created() {
    if (process.browser && !this.userData) {
      const { data } = await this.$get('/');
      if (data) this.$store.commit('setUserData', data);
    }
  },
  watch: {
    userData(val, oldVal) {
      if (val && val !== oldVal) {
        this.$router.push('/');
      }
    }
  },
  computed: {
    ...mapState(['userData'])
  }
};
</script>
