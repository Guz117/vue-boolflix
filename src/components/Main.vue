<template>
  <main>
    <div
      v-if="cards.length > 0"
      class="cards/"
    >
      <CardFilm
        v-for="(card, index) in cards"
        :key="index"
        :info="card"
      />
    </div>
    <div v-else>
      Nessun risultato
    </div>
  </main>
</template>

<script>
import CardFilm from './CardFilm.vue';

export default {
  name: 'Main',
  components: {
    CardFilm,
  },
  props: {
    cards: {
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