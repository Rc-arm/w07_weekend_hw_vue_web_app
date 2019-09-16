<template>
  <div id="app">
    <h1>Articles List App</h1>
    <div class="main-container">
      <articles-list :articles="articles"></articles-list>
      <article-detail :article="selectedArticle"></article-detail>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main'
import ArticleDetail from './components/ArticleDetail'
import ArticlesList from './components/ArticlesList'

export default {
  data(){
    return {
      articles: [],
      selectedArticle: null
    }
  },
  components: {
    "articles-list": ArticlesList,
    "article-detail": ArticleDetail
  },
  mounted(){
    // fetch('https://www.reddit.com/r/javascript.json')
    fetch('https://restcountries.eu/rest/v2/all')
    .then(result => result.json())
    .then(articles => this.articles = articles)

    eventBus.$on('article-selected', (article) => {
      this.selectedArticle = article
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
