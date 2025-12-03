<template>
  <div class="article-card">
    <b-card
      v-bind:title="article.title"
      v-bind:img-src="article.img"
      v-bind:img-alt="article.title"
      img-top
      tag="article"
      style="max-width: 20rem;"
      class="mb-2">
      <b-card-text>
        {{ article.body }}
      </b-card-text>
      <b-button href="#" variant="primary">Ver más</b-button>
    </b-card>
  </div>
</template>
<script>
export default {
  name: 'article-card',
  props: ['article']
}
</script>
<style scoped>
</style>
