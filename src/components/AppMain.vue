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
            store
        }
    }
}

</script>

<template lang="">

    <div class="container">
        <div class="row">
            <div v-for="(movie, index) in store.moviesList" v-bind:key="index" class="col-6 col-md-3 mb-2">
                {{ movie.title }}
                {{ movie.original_title }}
                {{ movie.original_language }}
                {{ movie.vote_count }}
            </div>
        </div>
    </div>

</template>

<style lang="">
 
</style>