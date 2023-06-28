<script>
export default {
 props: {
       mySerie: Object
   },
}
</script>

<template lang="">

    <div>
        <img :src="`https://image.tmdb.org/t/p/w342/${mySerie.poster_path}`">
        <ul>
            <li>Titolo Serie: <strong>{{ mySerie.name }}</strong></li>
            <li>Titolo Originale: <strong>{{ mySerie.original_name }}</strong></li>
            <li>Lingua: <strong>{{ mySerie.original_language }}</strong></li>
            <li>Voto: <strong>{{ mySerie.vote_average }}</strong></li>
        </ul>
    </div>

</template>

<style lang="">
 
</style>