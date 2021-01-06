<template>
  <div>
    <h3>news list</h3>
    <NuxtLink to="/news/1001">news</NuxtLink>
    <div v-for="news in newsList" :key="news.newsId">
      <NuxtLink :to="{ path: `/news/${news.newsId}` }">{{
        news.newsTitle
      }}</NuxtLink>
    </div>

    <br />
  </div>
</template>

<script>
export default {
  data() {
    return {
      newsList: [
        {
          newsId: 1001,
          newsTitle: "aaabbbccc",
        },
        {
          newsId: 1002,
          newsTitle: "aaabbbccc1002",
        },
      ],
    };
  },
};
</script>

<style></style>
