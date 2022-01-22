<template>
  <div class="card-film">
    <img
    v-if="info.poster_path == null" 
    :src="require('../assets/images/non_disponibile.jpg')" alt="">
    <img 
    v-else
    :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" alt="">
    <div class="description">
      <p>Title: {{ (info.title) ? info.title : info.name }}</p>
      <p>Original title: {{ (info.original_title) ? info.original_title : info.original_name }}</p>
      <p>Language: 
        <i :class="'flag flag-' + flag(info.original_language)" />
      </p>
      <p>Vote:
        <i :class="info.vote_average > 0 ? 'fas fa-star' : 'far fa-star' "></i>
        <i :class="info.vote_average > 3.5 ? 'fas fa-star' : 'far fa-star' "></i>
        <i :class="info.vote_average > 5.5 ? 'fas fa-star' : 'far fa-star' "></i>
        <i :class="info.vote_average > 7.5 ? 'fas fa-star' : 'far fa-star' "></i>
        <i :class="info.vote_average > 8.5 ? 'fas fa-star' : 'far fa-star' "></i>
      </p>
      <p>Overview: {{ info.overview }}</p>
    </div>
  </div>
</template>

<script>



export default {
  name: 'CardFilm',
  components: {
    
  },
  props: {
    info: Object,
  },
  methods: {
    flag(language) {
      if (language === 'en') {
        return 'us';
      }
      return language;
    },
  },
};
</script>

<style lang="scss">
@import '~mdb-ui-kit/css/mdb.min.css';
  i {
    color: yellow;
  }

  .description {
    color: white;
  }

   .card-film {
    width: 300px;
    height: 452px;
    position: relative;
    img {
      width: 100%;
      height: 100%;
    }
    .description{
      width: 100%;
      height: 452px;
      padding: 1em;
      overflow: auto;
      position: absolute;
      top: 0;
      background-color: black;
      opacity: 0.8;
      display: none;
    }
  }

  .card-film:hover .description{
    display: block;
  }

  
</style>