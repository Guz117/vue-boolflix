<template>
  <div id="app">
    <Header @searchFilm="search($event)" />
    <Main 
    :cards="cards"
    />
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return{
      query: 'https://api.themoviedb.org/3/search/',
      api_key: 'f5b95f9ba9397336a5f3db3b0f59503f',
      language: 'en-US',
      searchText: '',
      cards: [],
    };
  },
  methods: {
    setTextSearch(value) {
      this.searchText = value;
    },
    search(text) {
      this.searchText = text;
      this.getFilms();
      // this.getSeries();
    },
    getFilms() {
      const endpoint = 'movie';
      const parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.searchText,
      };

      axios.get(`${this.query}${endpoint}`, { params: parameters })
      .then((result) => {
        this.cards = result.data.results;
      })
      .catch((error) => console.log(error));
    },

    getSeries() {
      const endpoint = 'tv';
      const parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.searchText,
      };

      axios.get(`${this.query}${endpoint}`, { params: parameters })
      .then((result) => {
        this.cards = result.data.results;
      })
      .catch((error) => console.log(error));
    },
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
