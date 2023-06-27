<script>

import axios from 'axios';
import { store } from '../store.js'
import AppCard from './AppCard.vue';

export default {
    components: {
        AppCard
    },
    data() {
        return {
            moviesList: [],
            store
        }
    },
    
}

</script>

<template lang="">

    <div class="container">
        <div class="row">
            <div v-for="(movie, index) in store.moviesList" v-bind:key="movie.id" class="col-6 col-md-3 mb-2">
                <ul>
                    <li>Titolo: <strong>{{ movie.title }}</strong></li>
                    <li>Titolo Originale: <strong>{{ movie.original_title }}</strong></li>
                    <li>Lingua: <strong>{{ movie.original_language }}</strong></li>
                    <li>Voto: <strong>{{ movie.vote_count }}</strong></li>
                </ul>

                <!-- <AppCard :myMovie="movie"/> -->
            </div>
        </div>
    </div>

</template>

<style lang="">
 
</style>