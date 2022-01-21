<template>
  <div class="card-film">
    <p>{{ info.title }}</p>
    <p>{{ info.original_title }}</p>
    <p>
      <i :class="'flag flag-' + flag(info.original_language)" />
    </p>
    <p>{{ info.vote_average }}
       <i class="fas fa-star" :class="info.vote_average > 0 ? 'yellow' : 'grey' "></i>
      <i class="fas fa-star" :class="info.vote_average >= 4 ? 'yellow' : 'grey' "></i>
      <i class="fas fa-star" :class="info.vote_average >= 6 ? 'yellow' : 'grey' "></i>
      <i class="fas fa-star" :class="info.vote_average >= 8 ? 'yellow' : 'grey' "></i>
      <i class="fas fa-star" :class="info.vote_average >= 10 ? 'yellow' : 'grey' "></i>
    </p>
  </div>
</template>

<script>
// import { library } from '@fortawesome/fontawesome-svg-core'
// import { faStar } from '@fortawesome/free-solid-svg-icons'
// import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
// library.add(faStar)


export default {
  name: 'CardFilm',
  components: {
    // FontAwesomeIcon,
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

<style>
@import '~mdb-ui-kit/css/mdb.min.css';
  .yellow {
    color: yellow;
  }

  .grey {
    color:lightgrey;
  }
</style>