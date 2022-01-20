<template>
  <main>
    <div
      class="cards/"
    >
      <CardFilm
        v-for="(cardFilm, indexMovie) in cardsFilm"
        :key="indexMovie"
        :info="cardFilm"
      />
      <CardSeries
        v-for="(cardSeries, indexTv) in cardsSeries"
        :key="indexTv"
        :info="cardSeries"
      />

    </div>
  </main>
</template>

<script>
import CardFilm from './CardFilm.vue';
import CardSeries from './CardSeries.vue';

export default {
  name: 'Main',
  components: {
    CardFilm,
    CardSeries,
  },
  props: {
    cardsFilm: {
      type: Array,
      default() {
        return [];
      },
    },
    cardsSeries: {
      type: Array,
      default() {
        return [];
      },
    },
  },
};
</script>

<style lang="scss">
@import '~mdb-ui-kit/css/mdb.min.css';
</style>