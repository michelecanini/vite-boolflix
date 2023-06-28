<script>

export default {
    props: {
        myMovie: Object
    },
}

</script>

<template lang="">

    <div>
        <img :src="`https://image.tmdb.org/t/p/w342/${myMovie.poster_path}`">
        <ul>
            <li>Titolo Film: <strong>{{ myMovie.title }}</strong></li>
            <li>Titolo Originale: <strong>{{ myMovie.original_title }}</strong></li>
            <li>Lingua: <strong>{{ myMovie.original_language }}</strong></li>
            <li>Voto: <strong>{{parseInt(Math.round(myMovie.vote_average / 2))}}</strong></li>
        </ul>

    </div>
  
</template>

<style lang="" >
    
</style>