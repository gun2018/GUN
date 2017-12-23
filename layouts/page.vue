<template>
	<div>
		<top-bar></top-bar>
    <div>
      <nuxt/>
    </div>
		<a class="to-top-btn" href="#">
			<i class="iconfont icon-jiantoushang"></i>
    </a>
	</div>
</template>

<script>
import TopBar from '../components/TopBar.vue';
import { mapState } from 'vuex';

export default {
  components: { TopBar },
  async created() {
    if (process.browser && !this.userData) {
      const { data } = await this.$get('/');
      if (data) this.$store.commit('setUserData', data);
    }
  },
  computed: {
    ...mapState(['userData'])
  }

}
</script>