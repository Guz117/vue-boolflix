<template>
  <main>
    <div
      class="cards/"
    >
      <CardFilm
        v-for="(cardFilm, index) in cardsFilm"
        :key="index"
        :info="cardFilm"
      />
      <CardSeries
        v-for="(cardSeries, index) in cardsSeries"
        :key="index"
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

<style>

</style>