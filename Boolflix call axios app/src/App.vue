<template>
  <div id="app">
    <Header @doSearch="search($event)" />
    <Main :cards="cards" />
  </div>
</template>

<script>
// https://api.themoviedb.org/3/search/movie?api_key=2566b1c8b5bfbbe308497b0e3d8cd55b&query=
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'


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
      cards: []
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
