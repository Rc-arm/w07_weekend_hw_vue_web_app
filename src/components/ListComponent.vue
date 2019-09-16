<template lang="html">
  <li v-on:clink="handleClick">{{article.webTitle}}</li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['article'],
  methods: {
    handleClick(){
      eventBus.$emit('article-selected', this.selectedArticle)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
