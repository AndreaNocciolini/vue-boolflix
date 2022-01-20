<template>
  <div id="app">
    <i class="fas fa-star"></i>
    <Header @doSearch="search($event)" />
    <Main :cards="cards" />
  </div>
</template>

<script>
// https://api.themoviedb.org/3/search/movie?api_key=2566b1c8b5bfbbe308497b0e3d8cd55b&query=
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'

import { config } from '@fortawesome/fontawesome-svg-core'
console.log(config.autoA11y) // true
config.autoA11y = true
console.log(config.autoAddCss)
config.autoAddCss = true
console.log(config.observeMutations)
import {library } from '@fortawesome/fontawesome-svg-core'
import { fas } from '@fortawesome/free-solid-svg-icons'
import { fab } from '@fortawesome/free-brands-svg-icons'

import { findIconDefinition } from '@fortawesome/fontawesome-svg-core'
library.add(fas, fab)
const star = findIconDefinition({ prefix: 'fas', iconName: 'star' })
console.log(star.iconName)

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return {
      queryMovies: 'https://api.themoviedb.org/3/search/movie?',
      searchText: '',
      cards: [],
      starSupp: null
    }
  },
  created(){
  },
  methods: {
    search(text){
      if (text == ''){
        console.log('Empty Search')
        alert('Write something in the search bar')
      }
      else {
        this.searchText = text,
        this.getMovies()
      }
    },
    getMovies (){
      let parameters = {
        api_key:'2566b1c8b5bfbbe308497b0e3d8cd55b',
        language: 'it_IT',
        query: this.searchText,
      };
      axios.get(this.queryMovies, {params: parameters})
      .then((result)=> this.cards = result.data.results)
      .catch((error)=> console.log(error))
    }
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import '~mdb-ui-kit/css/mdb.min.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
