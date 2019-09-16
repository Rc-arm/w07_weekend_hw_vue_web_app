<template lang="html">
  <select v-on:change="handleChange" v-model="selectedArticle">
    <option v-for="article in articles" :value="article">{{article.webTitle}}</option>
  </select>
</template>

<script>
import ListComponent from './ListComponent'
// import { eventBus } from '../main'

export default {
  name: "articles-list",
  // data() {
  //   return {
  //     'selectedArticle': {}
  //   }
  // },
  props: ["articles"],
  components: {
    "list-component": ListComponent
  }
  // methods: {
  //   handleChange() {
  //     eventBus.$emit('article-selected', this.selectedArticle)
  //   }
  // }
}
</script>

<style lang="css" scoped>
</style>
