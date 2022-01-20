<template>
  <div class="card col-3 border-0">
      <div class="p-4 mt-3 bg-primary h-100 g-5 border-0">
        <h1>{{movie.title}}</h1>
        <h2>Original Title: {{movie.original_title}}</h2>
        <h3>Language: <i :class="'flag flag-' + getFlag(movie.original_language)"></i>{{movie.original_language}}</h3>
        <h4>Vote: {{movie.vote_average}}</h4>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        movie: Object,
    },
    methods: {
            getFlag(language) {
            if (language === 'en') {
                return 'us';
            }
            else {
                return language;
            }
        },
    }
}
</script>

<style lang="scss">
.card {
    display: flex;
    justify-content: space-around;
    align-items: baseline;
}
</style>