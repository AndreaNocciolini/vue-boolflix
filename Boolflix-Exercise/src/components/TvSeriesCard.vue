<template>
  <div class="col-3">
    <!-- <img src="" alt=""> -->
    <h1>Tv Series</h1>
    <h2>Title: {{name}}</h2>
    <h3>Original Title: {{originalName}}</h3>
    <h4>Language: <i :class="(language == 'en') ? 'flag flag-us' : 'flag flag-' + language"></i> {{language}}</h4>
    <h5>Likes: {{vote}}</h5>
  </div>
</template>

<script>
export default {
  name: 'TvSeriesCard',
  props: [
    'name',
    'originalName',
    'language',
    'vote'
  ]
}
</script>

<style>

</style>