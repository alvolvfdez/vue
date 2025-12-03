<template>
  <div class="articles">
    <b-button variant="success">{{ msg }}</b-button>
    <b-card-group columns id="list">
      <article-card v-for="article in articles"
                    v-bind:key="article.id"
                    v-bind:article="article"
      ></article-card>
    </b-card-group>
    <ul id="list">
      <li v-for="article in articles"
          v-bind:key="article.id"
          v-bind:article="article"
      >{{ article.id }} - {{ article.title }}
      </li>
    </ul>
  </div>
</template>
<script>
import ArticleCard from '@/components/ArticleCard'

const articlesList = [
  {
    id: 1,
    title: 'Lorem ipsum dolor sit',
    img: 'https://picsum.photos/300/150/?image=20',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam iaculis vulputate dui, in ultrices lorem aliquet quis. Aliquam at laoreet nibh, quis interdum magna. Nulla volutpat neque ut fermentum posuere.' },
  {
    id: 2,
    title: 'Morbi interdum sceler',
    img: 'https://picsum.photos/300/150/?image=21',
    body: 'Vestibulum lobortis ante non quam placerat pretium consectetur sit amet arcu. Vivamus eu tortor in mauris faucibus volutpat. Proin vel consectetur velit' },
  {
    id: 3,
    title: 'Morbi interdum sceler',
    img: 'https://picsum.photos/300/150/?image=22',
    body: 'Integer elit lacus, imperdiet vitae auctor in, mollis sed eros. Pellentesque eget augue et neque facilisis tristique.'
  },
  {
    id: 4,
    title: 'Morbi interdum sceler',
    img: 'https://picsum.photos/300/150/?image=23',
    body: 'Donec euismod, libero vitae tincidunt rutrum, ante justo tincidunt sapien, vitae egestas nisi libero vitae nisi.'
  },
  {
    id: 5,
    title: 'Morbi interdum sceler',
    img: 'https://picsum.photos/300/150/?image=24',
    body: 'Donec euismod, libero vitae tincidunt rutrum, ante justo tincidunt sapien, vitae egestas nisi libero vitae nisi.'
  },
  {
    id: 6,
    title: 'Morbi interdum sceler',
    img: 'https://picsum.photos/300/150/?image=25',
    body: 'Donec euismod, libero vitae tincidunt rutrum, ante justo tincidunt sapien, vitae egestas nisi libero vitae nisi.'
  }
]
export default {
  name: 'Articles',
  data () {
    return {
      msg: 'Listado de artículos',
      articles: articlesList
    }
  },
  components: {
    ArticleCard
  }
}
</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 10px;
}
</style>
