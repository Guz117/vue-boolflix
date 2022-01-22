<template>
  <div :class="copertina == 'visible' ? 'visible' : 'invisible'">
      <img class="boolflix-img" :src="require('../assets/images/logo.png')" alt=""> 
  </div>
</template>

<script>
export default {
    name: 'Copertina',
    data() {
        return {
            copertina: 'visible',
        }
    },
    created() {
      setTimeout(() => {
        this.copertina = 'invisible';
      }, 3000);
    },
}
</script>

<style lang="scss">
    .visible {
        background-color: black;
        width: 100vw;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        animation: copertinaOut 10s;
        .boolflix-img {
            width: 30%;
        }
    }

    .invisible {
        display: none;
    }

    @keyframes copertinaOut {
        from {
            opacity: 1;
        }
        to {
            opacity: 0.6;
        }
    }
</style>