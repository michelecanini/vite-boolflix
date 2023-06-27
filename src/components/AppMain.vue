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
            console.log(response.data);
        })
    }
}

</script>

<template lang="">
 <div>
  
 </div>
</template>

<style lang="">
 
</style>