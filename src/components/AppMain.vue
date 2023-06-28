<script>

import axios from 'axios';
import { store } from '../store.js'
import AppCardMovie from './AppCardMovie.vue';
import AppCardTv from './AppCardTv.vue';

export default {
    components: {
        AppCardMovie,
        AppCardTv
    },
    data() {
        return {
            store,
        }
    },
}

</script>

<template lang="">

    <div class="container"> 
        <div class="row">
            <div v-for="(movie, index) in store.moviesList" v-bind:key="movie.id" class="col-6 col-md-4 mb-2">
            
                 <AppCardMovie v-bind:myMovie="movie"/>

            </div>
            <div v-for="(serie, index) in store.tvSeriesList" v-bind:key="serie.id" class="col-6 col-md-4 mb-2">
            
                <AppCardTv v-bind:mySerie="serie"/>

            </div>
        </div>
    </div>

</template>

<style lang="scss">

 
</style>