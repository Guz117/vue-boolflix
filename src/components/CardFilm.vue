<template>
  <div class="card-film">
    <p>{{ info.title }}</p>
    <p>{{ info.original_title }}</p>
    <p>
      <i :class="'flag flag-' + flag(info.original_language)" />
    </p>
    <p>{{ info.vote_average }}
      <!-- <font-awesome-icon  icon="user-secret" /> -->
    </p>
  </div>
</template>

<script>
// import { library } from '@fortawesome/fontawesome-svg-core'
// import { faUserSecret } from '@fortawesome/free-solid-svg-icons'
// import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
// library.add(faUserSecret)

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
</style>