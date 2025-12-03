<template>
  <div class="article-detail">
    <b-container>
      <b-row>
        <b-col cols="12"><h1>{{ $route.params.id }} - {{article.title}}</h1></b-col>
      </b-row>
      <b-row>
        <b-col cols="12">
          <div class="image float-left"><img v-bind:src="article.img" v-bind:alt="article.title" /></div>
          <div v-html="article.body"></div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import {restConfig, siteDomain} from '@/App'
import axios from 'axios'

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
      article: [],
      siteDomain: siteDomain
    }
  },
  created () {
    axios
      .get(siteDomain + 'articulo/rest/' + this.$route.params.id, restConfig)
      .then(response => (this.article = response.data[0]))
  }
}
</script>
<style scoped>
image {
  padding: 20px;
}
</style>
