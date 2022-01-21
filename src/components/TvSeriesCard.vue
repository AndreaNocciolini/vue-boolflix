<template>
  <div class="col-3 mt-3">
    <div class="card-container p-3 d-flex justify-content-center align-items-center">
      <div class="img-container">
        <img :src="(img == null)? 'https://img.wallpapersafari.com/tablet/1536/2048/19/44/evOxST.jpg' :'https://image.tmdb.org/t/p/w300' + img" alt="">
      </div>
      <div class="description-container">
        <div class="description d-flex justify-content-between align-items-center">
          <h1>Tv Series</h1>
          <h2>Title: {{name}}</h2>
          <h3>Original Title: {{originalName}}</h3>
          <h3>Language: <i :class="(language == 'en') ? 'flag flag-us' : 'flag flag-' + language"></i> {{language}}</h3>
          <h5>Vote: <i v-for="(star,index) in 5" :key="index" :class="(index <= voteStars(vote))? 'fas fa-star' : 'far fa-star'"></i></h5>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TvSeriesCard',
  props: [
    'name',
    'originalName',
    'language',
    'vote',
    'img'
  ],
  methods: {
    voteStars(number) {
      const num = parseInt(number);
      return Math.round(num / 2);
    },
  }
}
</script>

<style lang="scss" scoped>
  img {
    width: 300px;
    height: 450px;
  }
</style>