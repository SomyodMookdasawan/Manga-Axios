<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/1.png" height="150px">
    <manga />
  </div>
</template>

<script>
import manga from './components/manga.vue'

export default {
  name: 'App',
  components: {
    manga,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body{
  background-image: url(https://i.pinimg.com/originals/59/75/d3/5975d3eea360f80ad53514c258542547.jpg);
  background-attachment: fixed;
  background-size: 100%;
}
</style>
