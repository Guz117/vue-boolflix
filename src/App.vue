<template>
  <div id="app">
    <Header @searchFilm="search($event)" />
    <Main 
    :cardsFilm="cardsMovie"
    :cardsSeries="cardsTv"
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
      cardsMovie: [],
      cardsTv: [],
      endpointMovie: 'movie',
      endpointTv:'tv',
    };
  },
  methods: {
    setTextSearch(value) {
      this.searchText = value;
    },
    search(text) {
      this.searchText = text;
        this.getSeries();
        this.getFilms();
    },
    getFilms() {
      const endpointMovie = this.endpointMovie;
      const parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.searchText,
      };

      axios.get(`${this.query}${endpointMovie}`, { params: parameters })
      .then((result) => {
        this.cardsMovie = result.data.results;
      })
      .catch((error) => console.log(error));
    },

    getSeries() {
      const endpointTv = this.endpointTv;
      const parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.searchText,
      };

      axios.get(`${this.query}${endpointTv}`, { params: parameters })
      .then((result) => {
        this.cardsTv = result.data.results;
      })
      .catch((error) => console.log(error));
    },
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
