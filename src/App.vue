<script>

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppCardMovie from './components/AppCardMovie.vue';
import AppCardTv from './components/AppCardTv.vue';
import { store } from './store.js';
import axios from 'axios';

export default {
    components: {
        AppHeader,
        AppMain,
        AppCardMovie,
        AppCardTv
    },
    data() {
        return {
            store,
        }
    },
    methods:{
    searchMovie() {
        // Svuota i risultati della ricerca precedente
        store.moviesList = [];
        store.tvSeriesList = [];

        let searchUrlComplete = `${store.moviesApiUri}?api_key=${store.apiKey}&query=${store.searchText}`;
        axios.get(searchUrlComplete).then ((response) => {
            if(response.data.results.length === 0){
                store.errorMessage = "Nessun film o serie tv trovati";
            } else {
                store.moviesList = response.data.results;
                store.errorMessage = "";
            }
        });

        let searchUrlCompleteTv = `${store.seriesApiUri}?api_key=${store.apiKey}&query=${store.searchText}`;
        axios.get(searchUrlCompleteTv).then ((response) => {
            if(response.data.results.length === 0){
                store.errorMessage = "Nessun film o serie tv trovati";
            } else {
                store.tvSeriesList = response.data.results;
                store.errorMessage = "";
            }
        });
    }
}


}

</script>

<template lang="">

    <div>
        <AppHeader @search="searchMovie" />
        <AppMain />
    </div>

</template>

<style lang="scss">

    @import './styles/generals.scss';
    @import '../node_modules/bootstrap/scss/bootstrap';

</style>