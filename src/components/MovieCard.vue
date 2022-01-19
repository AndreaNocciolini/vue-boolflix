<template>
  <div>
    <!-- <img src="" alt=""> -->
    <h1>{{title}}</h1>
    <h2>{{originalTitle}}</h2>
    <h3>{{language}}</h3>
    <h4>{{vote}}</h4>
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