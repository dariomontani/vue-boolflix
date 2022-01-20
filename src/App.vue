<template>
  <div id="app">
    <Header @searchFilm="getFilms($event)"/>
    <Main />
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
    }
  },

  methods: {
    getFilms(text){
      this.searchText = text;
      let end = "movie";
      let parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.searchText,
      };
      axios.get(`${this.queryApi}${end}`, {params: parameters}).then((result) => console.log(result)).catch((error) => console.log(error));
    }
  },
};
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
</style>
