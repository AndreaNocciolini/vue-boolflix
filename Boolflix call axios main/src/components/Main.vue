<template>
  <div>
    <Search 
      @clickSearch="searchMovie($event)"
      @enterSearch="searchMovie($event)"
    />
    <MovieCard 
      v-for="(movie, index) in movies"
      :key="index"
      :title="movie.title"
      :originalTitle="movie.original_title"
      :language="movie.original_language"
      :vote="movie.vote_count"
    />
  </div>
</template>

<script>
import MovieCard from './MovieCard.vue'
import Search from './Search.vue'
import axios from 'axios'

export default {
  name: 'Main',
  components: {
    MovieCard,
    Search,
  },
  data(){
    return {
      textSearch : '',
      movies: null,
      queryApiMovies: 'https://api.themoviedb.org/3/search/movie'
    }
  },
  methods: {
    searchMovie(text) {
      if(text == '') {
      this.movies = null
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
      })
    }
  }
}
</script>

<style>

</style>