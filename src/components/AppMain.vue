<script>

import axios from 'axios';

export default {
    data(){
        return{
            moviesList: []
        }
    },
    mounted(){
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=0c109132d12a812dd280ce879c2b7239&query=matrix').then ((response) => {
            this.moviesList = response.data.results;
        })
    }
}

</script>

<template lang="">

    <div class="container">
        <div class="row">
            <div v-for="(movie, index) in moviesList" v-bind:key="movie.id" class="col-6 col-md-4 mb-2">
                {{ movie.title }} <br>
                {{ movie.original_title }} <br>
                {{ movie.original_language }} <br>
                {{ movie.vote_count }} <br>
            </div>
        </div>
    </div>

</template>

<style lang="">
 
</style>