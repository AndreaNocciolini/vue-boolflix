<template>
  <div class="col-3">
    <!-- <img src="" alt=""> -->
    <h1>Tv Series</h1>
    <img :src="(img == null)? 'https://img.wallpapersafari.com/tablet/1536/2048/19/44/evOxST.jpg' :'https://image.tmdb.org/t/p/w300' + img"  alt="">
    <h2>Title: {{name}}</h2>
    <h3>Original Title: {{originalName}}</h3>
    <h4>Language: <i :class="(language == 'en') ? 'flag flag-us' : 'flag flag-' + language"></i> {{language}}</h4>
    <h5>Vote: {{vote}}</h5>
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
  ]
}
</script>

<style lang="scss">
  img {
    width: 300px;
    height: 450px;
  }
</style>