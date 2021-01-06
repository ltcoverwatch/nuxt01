<template>
  <div>
    <nav-top></nav-top>
    <div class="home-body">
      <el-row>
        <!-- hidden-xs-only要写在class里面，同时在nuxt.config里面引入样式表 -->
        <el-col class="hidden-xs-only" :sm="6" :md="6" :lg="6"
          >需要隐藏的侧边栏</el-col
        >
        <el-col class="article-content" :xs="24" :sm="18" :md="18" :lg="18">
          <p>
            不需要隐藏的文章看看一行有多少字看看一行有多少字看看一行有多少字看看一行有多少
          </p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
          <p>不需要隐藏的文章F</p>
        </el-col>
      </el-row>
    </div>
    <h3>article</h3>
    <p>路由传参：{{ articleId }}</p>
    <footer-bottom></footer-bottom>
  </div>
</template>

<script>
// import 'element-ui/lib/theme-chalk/display.css';
export default {
  data() {
    return {
      articleId: 0,
    };
  },
  created() {
    this.articleId = this.$route.query.articleId;
    console.log("created: ", this.articleId);
  },
};
</script>

<style>
@media screen and (max-width: 767px) {
  .article-content {
    margin: 6px 10px;
    /* line-height: 26px; */
  }
}
</style>
