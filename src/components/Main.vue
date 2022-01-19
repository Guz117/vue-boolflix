<template>
  <div>
      <Film
        v-for="(title, index) in titles"
        :key="index"
        :Titolo="title.title"
        :TitoloOriginale="title.original_title"
        :Lingua="title.original_language"
        :Voto="title.vote_average"
       />
  </div>
</template>

<script>
import axios from 'axios';
import Film from './Film';

export default {
    name: 'Main',
    components: {
        Film,
    },
    data() {
        return {
            titles: null,
        }
    },
    computed: {
        filteredTitle() {
            if (this.textSearch === '') {
                return this.titles;
            }
            return this.titles.filter((element) => element.title.toLowerCase().includes(this.textSearch.toLowerCase()));
        },  
        
    },
    mounted() {
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=f5b95f9ba9397336a5f3db3b0f59503f&query=ritorno+al+futuro')
        .then((result) => {
            console.log(result);
            this.titles = result.data.results
        })
        .catch ((error) => {
            console.log(error)
        })
    },
}

</script>

<style lang="scss">

</style>