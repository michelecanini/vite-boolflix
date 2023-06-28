<script>

import { store } from '../store.js'

export default {
    data() {
        return {
            store
        }
    }
}

</script>

<template lang="">

    <header>
        <div class="container d-flex justify-content-between">
            <div class="row d-flex "></div>
            <div class="col-3 mt-3 mb-3">
                <h1>BOOLFLIX</h1>
            </div>
            <div class="col-9 mt-3 mb-3">
                <div class="input-group">
                    <input type="search" class="form-control rounded" placeholder="Cerca Film e Serie TV" aria-label="Search" aria-describedby="search-addon" v-model="store.searchText" @keyup.enter="$emit('search')"/>
                    <button type="button" class="btn btn-outline-primary" @click="$emit('search')">search</button>
                </div>
            </div>
        </div>
    </header>

</template>

<style lang="">
 
</style>