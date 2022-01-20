<template>
  <div class="col-3">
    <!-- <img src="" alt=""> -->
    <h1>Movie</h1>
    <img :src="(img == null)? 'https://img.wallpapersafari.com/tablet/1536/2048/19/44/evOxST.jpg' :'https://image.tmdb.org/t/p/w300' + img" alt="">
    <h2>Title: {{title}}</h2>
    <h2>Original Title: {{originalTitle}}</h2>
    <h3>Language: <i :class="(language == 'en') ? 'flag flag-us' : 'flag flag-' + language"></i> {{language}}</h3>
    <h4>Likes: {{vote}}</h4>
  </div>
</template>

<script>
export default {
  name: 'MovieCard',
  props: [
    'title',
    'originalTitle',
    'language',
    'vote',
    'img'
  ]
}
</script>

<style lang="scss">
  img {
    width: 300px;
    height: 450px;
  }
</style>