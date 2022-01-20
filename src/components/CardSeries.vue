<template>
  <div class="card-film">
    <img :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`" alt="">
    <p>{{ info.original_name }}</p>
    <p>
      <i :class="'flag flag-' + flag(info.original_language)" />
    </p>
    <p>{{ info.vote_average }}</p>
  </div>
</template>

<script>
export default {
  name: 'CardSeries',
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

<style>
@import '~mdb-ui-kit/css/mdb.min.css';
</style>