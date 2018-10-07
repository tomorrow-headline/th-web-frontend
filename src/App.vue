<template>
  <div id="app">
    <Header></Header>
    <ArticleList></ArticleList>
  </div>
</template>

<script>
import Header from './components/Header'
import ArticleList from './components/ArticleList'

export default {
  name: 'app',
  components: {
    Header,
    ArticleList
  }
}
</script>

<style>
</style>
