<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
// https://api.themoviedb.org/3/search/movie?api_key=2566b1c8b5bfbbe308497b0e3d8cd55b&query=
import Header from './components/Header.vue'
import Main from './components/Main.vue'



export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      
    }
  },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>
