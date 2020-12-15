<template>
  <div>
    <h3>article</h3>
    <p>路由传参：{{ articleId }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articleId: 0,
    };
  },
  created() {
    this.articleId = this.$route.query.articleId;
    console.log('created: ', this.articleId)
  }
};
</script>

<style>
</style>