<template>
  <div class="search">
      <input
        id="search"
        v-model="inputText"
        type="text"
        name="search">
      <button
      type="submit"
      @click="$emit('doSearch', inputText)"
      >CERCA</button>
  </div>
</template>

<script>
export default {
    name: 'Search',
    data() {
    return {
      inputText: '',
    };
  },
}
</script>

<style>

</style>