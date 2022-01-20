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
    <TvSeriesCard 
      v-for="(tvShow, indexTV) in tvSeries"
      :key="indexTV"
      :name="tvShow.name"
      :originalName="tvShow.original_name"
      :language="tvShow.original_language"
      :vote="tvShow.vote_count"
    />
  </div>
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