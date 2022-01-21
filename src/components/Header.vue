<template>
  <div class="header">
      <h1>BOOLFLIX</h1>
      <div class="search">
      <input
        v-model="textSearch"
        type="text"
        placeholder="Film e Serie TV"
      >
      <button
        @click="$emit('searchFilm', textSearch)"
      >
        Cerca
      </button>
      
    </div>
  </div>
</template>

<script>
export default {
    name: 'Header',
    
    data() {
        return {
            textSearch: '',
        }
    },
}
</script>

<style lang="scss">
  .header {
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2em;
      h1 {
        color: red;
      }
  }


</style>