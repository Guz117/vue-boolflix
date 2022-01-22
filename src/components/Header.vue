<template>
  <div class="header">
      <img :src="require('../assets/images/logo.png')" alt="">
      <div class="search">
      <input
        v-model="textSearch"
        type="text"
        placeholder="Film e Serie TV"
      >
      <div class="button">
        <button
          @click="$emit('searchFilm', textSearch)"
        >
          <i class="fas fa-search"></i>
        </button>
      </div>
      
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
    width: 100%;
    position: fixed;
    z-index: 999;
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2em;
  }

  .search {
    width: 500px;
  }

  input {
    outline-color: red;
    width: 420px;
    border-radius: 10px;
  }

  .button {
    padding-left: 0.7em;
    display: inline;
    button {
      border-radius: 10px;
      background-color: rgb(211, 211, 211);
      .fa-search {
        color: red;
      }
    }
  }


</style>