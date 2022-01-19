<template>
  <div class="header">
      <h1>BOOLFLIX</h1>
      <Search 
        @doSearch="searchGenre($event)"
      />
  </div>
</template>

<script>
import Search from './Search';
export default {
    name: 'Header',
    components: {
        Search,
    },
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