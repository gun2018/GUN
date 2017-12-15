<style>
.news-container {
  width: 40%;
  background-color: #fff;
  margin: 0 auto;
}
</style>

<template>
  <div class="news-container">
    <div class="news-box">
      <h1 class="news-title">新闻题目</h1>
      <p class="news-detail">新闻描述</p>
      <img src="" class="news-img">
    </div>
  </div>
</template>

<script type="text/javascript">
export default {
  layout: 'page',
  validate({ params, query }) {
    console.log(params);
    
    return true;
  }
};
</script>