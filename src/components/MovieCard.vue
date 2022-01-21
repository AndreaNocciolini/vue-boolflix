<template>
  <div class="col-3">
    <!-- <img src="" alt=""> -->
    <h1>Movie</h1>
    <img :src="(img == null)? 'https://img.wallpapersafari.com/tablet/1536/2048/19/44/evOxST.jpg' :'https://image.tmdb.org/t/p/w300' + img" alt="">
    <h2>Title: {{title}}</h2>
    <h2>Original Title: {{originalTitle}}</h2>
    <h3>Language: <i :class="(language == 'en') ? 'flag flag-us' : 'flag flag-' + language"></i> {{language}}</h3>
    <h5>Vote: <i v-for="(star,index) in voteStars(vote)" :key="index" class="fas fa-star"></i></h5>
  </div>
</template>

<script>
export default {
  name: 'MovieCard',
  components: {
  },
  props: [
    'title',
    'originalTitle',
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

<style lang="scss">

  img {
    width: 300px;
    height: 450px;
  }
</style>