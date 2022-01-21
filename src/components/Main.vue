<template>
  <main class="row">
    <MovieCard 
      v-for="(movie, index) in movies"
      :key="index"
      :img="movie.poster_path"
      :title="movie.title"
      :originalTitle="movie.original_title"
      :language="movie.original_language"
      :vote="movie.vote_average"
    />
    <TvSeriesCard 
      v-for="(tvShow, index) in tvSeries"
      :key=" 'TV' + index"
      :img="tvShow.poster_path"
      :name="tvShow.name"
      :originalName="tvShow.original_name"
      :language="tvShow.original_language"
      :vote="tvShow.vote_average"
    />
  </main>
</template>

<script>
import MovieCard from './MovieCard.vue'
import TvSeriesCard from './TvSeriesCard.vue'


export default {
  name: 'Main',
  props: {
    movies: {},
    tvSeries: {}
  },
  components: {
    MovieCard,
    TvSeriesCard
  },
  
}
</script>

<style>

</style>