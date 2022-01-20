<template>
  <div class="row">
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


export default {
  name: 'Main',
  props: {
    movies: {}
  },
  components: {
    MovieCard,
  },
  
}
</script>

<style>

</style>