<template>
  <div id="app">
    <Header @searchFilm="search($event)"/>
    <Main :cards="cards"/>
    <Footer />
  </div>
</template>

<script>
import axios from "axios";

import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue"


export default {
  name: "App",
  components: {
    Header,
    Main,
    Footer,
  },

  data(){
    return{
      queryApi: "https://api.themoviedb.org/3/search/",
      api_key: "9505cc46166ebdcfaaeb4f17e2cdaa20",
      language: "en-US",
      searchText: "",
      cards: [],
      movies: [],
      series: [],
    }
  },

  methods: {
    search(text){
      this.searchText = text;
      this.getFilms();
      this.getTvSeries();
    },
    
    getFilms(){
      let end = "movie";
      let parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.searchText,
      };
      axios.get(`${this.queryApi}${end}`, {params: parameters}).then((result) => {
        this.movies = result.data.results;
        this.cards = [...this.movies,...this.series];
      }).catch((error) => console.log(error));
    },

    getTvSeries(){
      let end = "tv";
      let parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.searchText,
      };
      axios.get(`${this.queryApi}${end}`, {params: parameters}).then((result) => {
        this.series = result.data.results;
        this.cards = [...this.movies,...this.series];
      }).catch((error) => console.log(error));
    }
  },
};
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
</style>
