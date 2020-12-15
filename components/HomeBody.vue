<template>
  <div class="home-body">
    <el-row class="product-center" :gutter="20">
      <el-col :xs="24" :sm="12" :md="12" :lg="12">
        <NuxtLink to="/about">
          <!-- 相对路径时用require -->
          <el-image
            style="width: 100%"
            :src="require('@/assets/img/zoom01.PNG')"
            fit="contain"
          ></el-image
        ></NuxtLink>
      </el-col>
      <el-col :xs="24" :sm="12" :md="12" :lg="12">
        <!-- 地址栏带参数，用query，否则用params -->
        <NuxtLink
          target="_blank"
          :to="{ path: '/article', query: { articleId: 1001 } }"
        >
          <el-image
            style="width: 100%"
            :src="require('@/assets/img/zoom02.PNG')"
            fit="contain"
          ></el-image
        ></NuxtLink>
      </el-col>
    </el-row>
    <el-row class="industry-application" :gutter="20">
      <el-col :xs="12" :sm="8" :md="4" :lg="4">
        <div>a</div>
      </el-col>
      <el-col :xs="12" :sm="8" :md="4" :lg="4">
        <div>a</div>
      </el-col>
      <el-col :xs="12" :sm="8" :md="4" :lg="4">
        <div>a</div>
      </el-col>
      <el-col :xs="12" :sm="8" :md="4" :lg="4">
        <div>a</div>
      </el-col>
      <el-col :xs="12" :sm="8" :md="4" :lg="4">
        <div>a</div>
      </el-col>
      <el-col :xs="12" :sm="8" :md="4" :lg="4">
        <div>a</div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {};
</script>

<style>
.home-body {
  max-width: 1200px;
  margin: 10px auto;
}
.product-center {
  background-color: pink;
}
.industry-application {
  background-color: skyblue;
}
</style>