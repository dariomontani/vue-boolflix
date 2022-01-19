<template>
  <div id="app">
    <Header @search="searchFilm"/>
    <Main />
  </div>
</template>

<script>
import axios from 'axios';

import Header from "./components/Header.vue";
import Main from "./components/Main.vue";


export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data(){
    return{
      queryApi: 'https://api.themoviedb.org/3/search/movie?api_key=9505cc46166ebdcfaaeb4f17e2cdaa20&query=ritorno+al+futuro',
      films: [],
    }
  },
  created() {
    axios.get(this.queryApi)
      .then((result) => {
        this.films = result.results;
        console.log(result.results);
      })
      .catch((error) => {
        console.log(error);
      })
  },
};
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
</style>
