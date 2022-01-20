<template>
  <div class="col-3">
    <!-- <img src="" alt=""> -->
    <h1>Title: {{title}}</h1>
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
    'vote'
  ]
}
</script>

<style>

</style>