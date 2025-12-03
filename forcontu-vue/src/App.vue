<template>
  <div id="app">
    <b-navbar type="dark" variant="info">
      <b-navbar-nav>
        <b-nav-item :to="{ name: 'Articles' }">Artículos</b-nav-item>
      </b-navbar-nav>
    </b-navbar>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.navbar {
  margin-bottom: 20px;
}
</style>
