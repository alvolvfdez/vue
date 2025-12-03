<template>
  <div class="article-detail">
    <b-container>
      <b-row>
        <b-col cols="12"><h1>{{ $route.params.id }} - {{article.title}}</h1></b-col>
      </b-row>
      <b-row>
        <b-col cols="12">
          <div class="image float-left"><img v-bind:src="article.img" vbind:alt="article.title" /></div>
          <div v-html="article.body"></div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
const article = {
  id: 11,
  title: 'Lorem ipsum dolor sit amet',
  body: '<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. </p>...',
  img: '//picsum.photos/500/300?random'
}
export default {
  name: 'article-detail',
  data () {
    return {
      article: article
    }
  }
}
</script>
<style scoped>
image {
  padding: 20px;
}
</style>
