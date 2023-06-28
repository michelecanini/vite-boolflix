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
            store,
        }
    },
}

</script>

<template lang="">

    <div class="container"> 
        <div class="row">
            <div v-for="(movie, index) in store.moviesList" v-bind:key="movie.id" class="col-6 col-md-4 mb-2">
            
                 <AppCard v-bind:myMovie="movie"/>
                 
            </div>
        </div>
    </div>

</template>

<style lang="scss">

 
</style>