<template>
  <div class="article-detail">
    <p v-if="loading">Loading...</p>
    <b-container v-else>
      <b-row>
        <b-col cols="12"><h1>{{ $route.params.id }} - {{article.title}}</h1></b-col>
      </b-row>
      <b-row>
        <b-col cols="12">
          <div class="image float-left"><img v-bind:src="siteDomain + article.img" v-bind:alt="article.title" /></div>
          <div v-html="article.text"></div>
        </b-col>
      </b-row>
      <b-row>
        <b-col cols="12">
          <p>
            Enviado por {{ article.user }}
            el {{ formatDate(article.created) }}
          </p>

          <p v-if="article.changed !== article.created">
            Última modificación: {{ formatDate(article.changed) }}
          </p>
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
  },
  methods: {
    formatDate(date) {
      const d = new Date(date)
      const day = String(d.getDate()).padStart(2, '0')
      const month = String(d.getMonth() + 1).padStart(2, '0')
      const year = d.getFullYear()
      const hours = String(d.getHours()).padStart(2, '0')
      const minutes = String(d.getMinutes()).padStart(2, '0')
      return `${day}/${month}/${year} - ${hours}:${minutes}`
    }
  }
}
</script>
<style scoped>
image {
  padding: 20px;
}
</style>
