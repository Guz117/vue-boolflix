<template>
  <main class="cont">
    <div
      class="cards"
    >
      <CardFilm 
        v-for="(cardFilm, indexMovie) in cardsFilm"
        :key="indexMovie+cardFilm.id"
        :info="cardFilm"
      />
      <CardFilm 
        v-for="(cardSeries, indexSeries) in cardsSeries"
        :key="indexSeries+cardSeries.id"
        :info="cardSeries"
      />

    </div>
  </main>
</template>

<script>
import CardFilm from './CardFilm.vue';
// import CardSeries from './CardSeries.vue';

export default {
  name: 'Main',
  components: {
    CardFilm,
    // CardSeries,
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
  main {
    width: 100%;
    height: 100vh;
    background: url('../assets/images/sfondo.jpg');
  }

  .cards {
    width: 100vw;
    padding-top: 8em;
    padding-bottom: 2em;
    background: url('../assets/images/sfondo.jpg');
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
  }
</style>