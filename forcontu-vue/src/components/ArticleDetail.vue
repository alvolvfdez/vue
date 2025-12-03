<template>
  <div class="article-detail">
    <p v-if="loading">Loading...</p>
    <b-container v-else>
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

export default {
  name: 'article-detail',
  data () {
    return {
      article: [],
      siteDomain: siteDomain,
      loading: false
    }
  },
  created () {
    this.loading = true
    axios
      .get(siteDomain + 'articulo/rest/' + this.$route.params.id, restConfig)
      .then(response => {
        this.article = response.data[0]
        this.loading = false
      })
  }
}
</script>
<style scoped>
image {
  padding: 20px;
}
</style>
