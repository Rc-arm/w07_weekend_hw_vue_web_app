<template lang="html">
  <select v-on:change="handleChange" v-model="selectedArticle">
    <option v-for="article in articles" :value="article">{{article.title}}</option>
  </select>
</template>

<script>
  import { eventBus } from '../main'

export default {
  name: "articles-list",
  data() {
    return {
      'selectedArticle': {}
    }
  },
  props: ["articles"],
  methods: {
    handleChange() {
      eventBus.$emit('article-selected', this.selectedArticle)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
