<template>
<div class="ArticleCard">
  <h2 class="ArticleTitle">{{ article.title }}</h2>
  <div class="ArticleExcerpt">{{ article.excerpt }}</div>
  <div class="ArticleActions">
    <span>
      <button aria-label="Like!" type="button" class="btn btn-success">Like!</button>
      <button aria-label="Like!" type="button" class="btn btn-danger">Dislike.</button>
    </span>
    <button type="button" class="btn btn-link">Add comment.</button>
  </div>
</div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import '../plugins/axios'

export default {
  name: 'ArticleCard',
  props: {
    article: {}
  },
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.ArticleCard {
  -webkit-tap-highlight-color: rgba(26, 26, 26, 0);
  font-size: 15px;
  color: #1a1a1a;
  background: #fff;
  overflow: hidden;
  border-radius: 2px;
  box-sizing: border-box;
  position: relative;
  padding: 20px;
  margin-bottom: 0;
  box-shadow: none;
  border-bottom: 1px solid #f0f2f7;
}

.ArticleTitle {
  -webkit-tap-highlight-color: rgba(26, 26, 26, 0);
  display: block;
  margin-block-end: 0.83em;
  margin-block-start: 0.83em;
  margin-inline-end: 0;
  margin-inline-start: 0;
  margin: 0;
  font: inherit;
  margin-bottom: -4px;
  margin-top: -4px;
  color: #1a1a1a;
  line-height: 1.6;
  font-weight: 600;
  font-size: 18px;
}

.ArticleExcerpt {
  font-family: -apple-system, BlinkMacSystemFont, Helvetica Neue, PingFang SC,
    Microsoft YaHei, Source Han Sans SC, Noto Sans CJK SC, WenQuanYi Micro Hei,
    sans-serif;
  font-size: 15px;
  color: #1a1a1a;
  -webkit-tap-highlight-color: rgba(26, 26, 26, 0);
  display: block;
  line-height: 1.67;
  cursor: pointer;
  transition: color 0.14s ease-out;
  overflow: hidden;
  margin-bottom: -4px;
  margin-top: 16px;
  max-height: 100px;
}

.ArticleActions {
  font-family: -apple-system, BlinkMacSystemFont, Helvetica Neue, PingFang SC,
    Microsoft YaHei, Source Han Sans SC, Noto Sans CJK SC, WenQuanYi Micro Hei,
    sans-serif;
  font-size: 15px;
  color: #1a1a1a;
  background: #f6f6f6;
  -webkit-tap-highlight-color: rgba(26, 26, 26, 0);
  line-height: 1.67;
  cursor: pointer;
  transition: color 0.14s ease-out;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  padding: 10px 20px;
  margin: 0 -20px -10px;
  color: #646464;
  background: #fff;
  clear: both;
}
</style>
