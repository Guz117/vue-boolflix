<template>
  <div>
    <div class="film">
        <h3>{{ Titolo }}</h3>
        <h3>{{ TitoloOriginale }}</h3>
        <h3>{{ Lingua }}</h3>
        <h3>{{ Voto }}</h3>
    </div>   
  </div>
</template>

<script>
export default {
    name: 'Film',
    props: [
        'Titolo',
        'TitoloOriginale',
        'Lingua',
        'Voto',
    ]
}

</script>

<style>

</style>