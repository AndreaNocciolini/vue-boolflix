<template>
  <div id="app">
    <Header @calldoSearch="searchMovie($event)"/>
    <Main :movies="movies" :tvSeries="tvSeries" />
  </div>
</template>

<script>
// https://api.themoviedb.org/3/search/movie?api_key=2566b1c8b5bfbbe308497b0e3d8cd55b&query=
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return {
      textSearch : '',
      tvSeries: null,
      movies: null,
      queryApiMovies: 'https://api.themoviedb.org/3/search/movie',
      queryApiSeries: 'https://api.themoviedb.org/3/search/tv',
    }
  },
  methods: {
    searchMovie(text) {
      if(text == '') {
        this.movies = null
        this.tvSeries = null
      }
      else {
        this.textSearch = text
        this.callAxios()
      }
    },
    callAxios(){
      axios.get(this.queryApiMovies, {
        params: {
          api_key:'2566b1c8b5bfbbe308497b0e3d8cd55b',
          language: 'en-US',
          query: this.textSearch
        }
      })
      .then(results => {
        this.movies = results.data.results
      })
      .catch ((error) => {
        console.log(error)
      }),
      axios.get(this.queryApiSeries, {
        params: {
          api_key:'2566b1c8b5bfbbe308497b0e3d8cd55b',
          language: 'en-US',
          query: this.textSearch
        }
      })
      .then(results => {
        this.tvSeries = results.data.results
      })
      .catch ((error) => {
        console.log(error)
      })
    }
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import '~mdb-ui-kit/css/mdb.min.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>
