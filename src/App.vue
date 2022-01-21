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

html {
  background-color: #434343;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #434343;
}

// START scss component --Card
.fas.fa-star {
  color: #FFFF00;
}

.card-container{
    position: relative;
    color: white;
    text-align: center;
		display: flex;
		flex-direction: column;
		align-items: center;
		height: 100%;
    border: 1px solid white;
  }

  .description-container {
    display: none;
    position: absolute;
    background-color: grey;
    opacity: 0.9;
    height: 100%;
    width: 100%;
    cursor: pointer;
    .description {
      overflow: auto;
      height: 100%;
      padding: 0.5em;
      opacity: 1;
      flex-direction: column;
    }
  }

  

  .card-container:hover .description-container {
    display: block;
  }
  // END scss component --Card
</style>