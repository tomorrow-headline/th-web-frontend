<template>
  <div id="ArticleList">
    <ArticleCard v-for="article of articleList" :key="article.title" :article="article"></ArticleCard>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import ArticleCard from './ArticleCard.vue'

export default {
  name: 'ArticleList',
  components: {
    ArticleCard
  },
  data: function () {
    return {
      articleList: []
    }
  },
  methods: {
    getArticleList: function () {
      this.axios
        .get('/api/news/articles/')
        .then(response => {
          this.articleList = response.data
        })
        .catch(error => console.error(error))
    }
  },
  mounted: function () {
    this.getArticleList()
  }
}
</script>

<style>
</style>
