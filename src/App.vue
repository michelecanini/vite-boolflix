<script>

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppCard from './components/AppCard.vue';
import { store } from './store.js';
import axios from 'axios';


export default {
    components: {
        AppHeader,
        AppMain,
        AppCard
    },
    data() {
        return {
            store,
        }
    },
    methods:{

        searchMovie() {
            let searchUrlComplete = `${store.moviesApiUri}?api_key=${store.apiKey}&query=${store.searchText}`;
            axios.get(searchUrlComplete).then ((response) => {
                store.moviesList = response.data.results;
            })
        }
    }
}

</script>

<template lang="">

  <div>
    <AppHeader @search="searchMovie" />
    <AppMain />
    <!--<AppCard /> -->
  </div>

</template>

<style lang="scss">

    @import './styles/generals.scss';
    @import '../node_modules/bootstrap/scss/bootstrap';

</style>