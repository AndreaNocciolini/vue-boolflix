<template>
  <div class="col-3">
    <!-- <img src="" alt=""> -->
    <h1>Movie</h1>
    <img :src="(img == null)? 'https://img.wallpapersafari.com/tablet/1536/2048/19/44/evOxST.jpg' :'https://image.tmdb.org/t/p/w300' + img" alt="">
    <h2>Title: {{title}}</h2>
    <h2>Original Title: {{originalTitle}}</h2>
    <h3>Language: <i :class="(language == 'en') ? 'flag flag-us' : 'flag flag-' + language"></i> {{language}}</h3>
    <h4>Likes: <font-awesome-icon icon="star"></font-awesome-icon>{{voteStars(vote)}}</h4>
  </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { faStar } from '@fortawesome/free-solid-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

library.add(faStar)

export default {
  name: 'MovieCard',
  components: {
    FontAwesomeIcon,
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