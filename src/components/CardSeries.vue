<template>
  <div class="card-film">
    <p>{{ info.original_name }}</p>
    <p>{{ info.original_language }}</p>
    <p>{{ info.vote_average }}</p>
  </div>
</template>

<script>
export default {
  name: 'CardSeries',
  props: {
    info: Object,
  },
};
</script>

<style>

</style>